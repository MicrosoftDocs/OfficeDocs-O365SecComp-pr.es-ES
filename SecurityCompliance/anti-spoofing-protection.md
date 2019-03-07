---
title: Protección contra suplantación de identidad en Office 365
ms.author: tracyp
author: MSFTtracyp
manager: laurawi
ms.date: 3/6/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: En este artículo se describe cómo Office 365 mitiga los ataques de suplantación de identidad (phishing) que usan dominios de remitente falsificados, es decir, dominios que se falsifican. Para ello, se analizan los mensajes y se bloquean los que no se pueden autenticar a través de los métodos de autenticación de correo electrónico estándar, ni de otras técnicas de reputación del remitente. Este cambio se implementó para reducir el número de ataques de suplantación de identidad a los que se exponen las organizaciones de Office 365.
ms.openlocfilehash: 422bac2ad5fd0c58928d79467721204b20583fd7
ms.sourcegitcommit: 5d6be2b208dbe28d5d5da057c60cf97729799c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30465487"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Protección contra suplantación de identidad en Office 365

En este artículo se describe cómo Office 365 mitiga los ataques de suplantación de identidad (phishing) que usan dominios de remitente falsificados, es decir, dominios que se falsifican. Para ello, analiza los mensajes y bloquea los que no se pueden autenticar con los métodos de autenticación de correo electrónico estándar, ni con otras técnicas de reputación del remitente. Este cambio se implementó para reducir el número de ataques de suplantación de identidad a los que se exponen las organizaciones de Office 365.
  
En este artículo también se describe por qué se realiza este cambio, cómo los clientes pueden prepararse para este cambio, cómo ver los mensajes que se verán afectados, cómo informar sobre los mensajes, cómo mitigar los falsos positivos y cómo deben prepararse los remitentes a Microsoft para este cambie.
  
La tecnología contra la suplantación de identidad de Microsoft se implementó inicialmente en sus organizaciones con una suscripción a Office 365 Enterprise E5 o compró el complemento de protección contra amenazas avanzada (ATP) de Office 365 para su suscripción. A partir de octubre, 2018 amplié la protección a las organizaciones que también tienen Exchange Online Protection (EOP). Además, debido a la forma en que todos los filtros se aprenden entre sí, los usuarios de Outlook.com también pueden verse afectados.
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Uso de la suplantación de identidad en ataques de suplantación de identidad

Cuando se trata de proteger a sus usuarios, Microsoft aprovecha seriamente la amenaza que supone la suplantación de identidad. Una de las técnicas que suelen usar los remitentes de correo no deseado y los phish es la suplantación de identidad, que es cuando el remitente está falsificado y un mensaje parece provenir de alguien o en algún lugar que no sea el origen real. Esta técnica se suele usar en las campañas de suplantación de identidad diseñadas para obtener las credenciales del usuario. La tecnología contra la suplantación de identidad de Microsoft examina específicamente la falsificación del encabezado ' from: header ', que es la que se muestra en un cliente de correo electrónico como Outlook. Cuando Microsoft tiene la confianza alta en que el encabezado de: está falseado, identifica el mensaje como una suplantación de identidad.
  
Los mensajes de suPlantación de identidad tienen dos implicaciones negativas para los usuarios de la vida real:
  
### <a name="1-spoofed-messages-deceive-users"></a>1. los mensajes suPlantados pueden engañar a los usuarios
  
En primer lugar, un mensaje falsificado puede engañar a un usuario para que haga clic en un vínculo y dar su credencial, descargar malware o responder a un mensaje con contenido confidencial (este último se conoce como compromiso de correo electrónico empresarial). Por ejemplo, el siguiente es un mensaje de suplantación de identidad (phishing) con un remitente falso de msoutlook94@service.outlook.com:
  
![Suplantación de mensajes de suplantación service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
En realidad, lo anterior no procedía de service.outlook.com, sino que fue suplantado por el phish para que parezca que lo hacía. Está intentando engañar a un usuario para que haga clic en el vínculo del mensaje.
  
El siguiente ejemplo es la suplantación de contoso.com:
  
![Mensaje de suPlantación de identidad: compromiso de correo electrónico empresarial](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
El mensaje parece legítimo, pero de hecho es una falsa simulación. Este mensaje de suplantación de identidad es un tipo de compromiso de correo electrónico empresarial que es una subcategoría de la suplantación de identidad.

### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. los usuarios confunden mensajes reales para falsos
  
En segundo lugar, los mensajes suplantados crean incertidumbre para los usuarios que saben los mensajes de suplantación de identidad (phishing) pero no pueden distinguir la diferencia entre un mensaje real y los suplantados en uno. Por ejemplo, el siguiente es un ejemplo de restablecimiento real de contraseñas desde la dirección de correo electrónico de la cuenta de seguridad de Microsoft:
  
![Restablecimiento de contraseña legítima de Microsoft](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
El mensaje anterior procedía de Microsoft, pero al mismo tiempo, los usuarios se utilizan para obtener mensajes de suplantación de identidad (phishing) que pueden engañar a un usuario para que haga clic en un vínculo y dar su credencial, descargar malware o responder a un mensaje con contenido confidencial. Debido a que es difícil identificar la diferencia entre un restablecimiento de contraseña real y uno falso, muchos usuarios ignoran estos mensajes, los informan como correo no deseado o innecesariamente notificar los mensajes a Microsoft como estafas de suplantación de identidad (phishing) perdidas.

Para detener la suplantación, el sector de filtrado de correo electrónico ha desarrollado protocolos de autenticación de correo electrónico, como [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)y [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email). DMARC impide la suplantación de identidad examinando el remitente de un mensaje (el que ve el usuario en su cliente de correo electrónico) (en los ejemplos anteriores, es service.outlook.com, outlook.com y accountprotection.microsoft.com)-con el dominio que pasó SPF o DKIM. Es decir, el dominio que el usuario ve se ha autenticado y, por lo tanto, no está falsificado. Para obtener una explicación más completa, consulte la sección "*Descripción del motivo por el que la autenticación de correo electrónico no siempre es suficiente para detener* la suplantación" más adelante en este artículo.
  
Sin embargo, el problema es que los registros de autenticación de correo electrónico son opcionales, no obligatorios. Por lo tanto, aunque los dominios con directivas de autenticación firme como microsoft.com y skype.com están protegidos contra la suplantación de identidad, los dominios que publican directivas de autenticación más débiles o no tienen ninguna directiva, son objetivos de suplantación de identidad. A partir del 2018 de marzo, solo el 9% de los dominios de las empresas de la Fortune 500 publican directivas de autenticación de correo electrónico seguras. El 91% restante puede ser falsificado por un phish y, a menos que el filtro de correo electrónico lo detecte con otra directiva, se entregue a un usuario final y se engañará:
  
![Directivas de DMARC de las empresas del ranking Fortune 500](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
La proporción de pequeñas y medianas empresas que no se encuentran en la Fortune 500 que publican directivas de autenticación de correo electrónico seguras es más pequeña y menor todavía para dominios que se encuentran fuera de Norteamérica y Europa occidental.
  
Se trata de un problema importante porque, si bien las empresas no saben cómo funciona la autenticación de correo electrónico, los phishistas entienden y aprovechan la falta de la autenticación.
  
Para obtener información sobre la configuración de SPF, DKIM y DMARC, consulte la sección "*clientes de Office 365"* más adelante en este documento. 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>Detención de la suplantación con autenticación de correo electrónico implícita

Debido a que la suplantación de identidad (phishing) y la suplantación de identidad (phishing) de Spear son un problema, y debido a la limitada adopción de directivas de autenticación de correo electrónico seguras, Microsoft sigue invirtiendo en capacidades para proteger Por lo tanto, Microsoft está avanzando con la *autenticación de correo electrónico implícita* : Si un dominio no se autentica, Microsoft lo tratará como si hubiera publicado registros de autenticación de correo electrónico y los trataría en consecuencia si no se supera. 
  
Para ello, Microsoft ha creado numerosas extensiones para la autenticación de correo electrónico normal, incluidas la reputación del remitente, el historial del remitente/destinatario, el análisis del comportamiento y otras técnicas avanzadas. Un mensaje que se envía desde un dominio que no publica la autenticación de correo electrónico se marca como falso a menos que contenga otras señales para indicar que es legítimo.
  
De esta forma, los usuarios finales pueden tener la certeza de que un correo electrónico que se envía a ellos no se ha falseado, los remitentes pueden tener la certeza de que nadie está suplantando su dominio y los clientes de Office 365 pueden ofrecer una mejor protección, como la protección de suplantación.
  
Para ver el anuncio general de Microsoft, vea [un mar de phish parte 2: protección mejorada contra la suplantación de identidad en Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>Identificación de que un mensaje se clasifica como simulado

### <a name="composite-authentication"></a>Autenticación compuesta

Aunque SPF, DKIM y DMARC son útiles por sí mismos, no comunican el estado de autenticación suficiente en el caso de que un mensaje no tenga registros de autenticación explícitos. Por lo tanto, Microsoft ha desarrollado un algoritmo que combina varias señales en un único valor denominado autenticación compuesta o compauth para abreviar. Los clientes de Office 365 tienen compauth valores marcados en el encabezado *Authentication-Results* en los encabezados del mensaje. 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**Resultado CompAuth**|**Descripción**|
|:-----|:-----|
|interrumpi|Error en el mensaje autenticación explícita (envío de registros publicados de dominio explícitamente en DNS) o autenticación implícita (el dominio de envío no publicó registros en DNS, por lo que Office 365 interpolaba el resultado como si hubiera publicado registros publicados).|
|DV|El mensaje ha pasado una autenticación explícita (el mensaje ha superado DMARC o [dMarc que ha pasado](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)una adivinación) o la autenticación implícita con alta confianza (el dominio de envío no publica los registros de autenticación de correo electrónico, pero Office 365 tiene señales back-end de gran rendimiento) para indica que el mensaje es probable que sea legítimo).|
|softpass|El mensaje pasó la autenticación implícita con una confianza baja a media (el dominio de envío no publica la autenticación de correo electrónico, pero Office 365 tiene señales de back-end para indicar que el mensaje es legítimo, pero la fuerza de la señal es más débil).|
|ninguna|El mensaje no se autenticó (o se autenticó pero no se alinea), pero no se aplicó la autenticación compuesta debido a la reputación del remitente u otros factores.|
   
|||
|:-----|:-----|
|**Motivo**|**Descripción**|
|0xx|Error en el mensaje de autenticación compuesta.<br/>**000** significa que el mensaje produjo un error de DMARC con una acción de rechazar o poner en cuarentena.  <br/>**001** significa que el mensaje no pudo realizar la autenticación implícita de correo electrónico. Esto significa que el dominio de envío no tenía registros de autenticación de correo electrónico publicada o, si lo hicieron, tenía una directiva de error más débil (error de SPF o un error de la Directiva de DMARC? o neutral, la Directiva de DMARC de p = None).  <br/>**002** significa que la organización tiene una directiva para el par remitente/dominio que está explícitamente prohibida para el envío de correo electrónico falsificado; un administrador establece manualmente esta configuración.  <br/>**010** significa que el mensaje produjo un error de DMARC con una acción de rechazar o poner en cuarentena, y el dominio de envío es uno de los dominios aceptados de la organización (esto es parte de la suplantación de identidad o de una imitación).  <br/>**011** significa que el mensaje no pudo realizar la autenticación implícita del correo electrónico y el dominio de envío es uno de los dominios aceptados de la organización (esto es parte de la suplantación de identidad o de una imitación).|
|Todos los demás códigos (1xx, 2xx, 3xx, 4xx, 5xx)|Corresponde a diversos códigos internos por los cuales un mensaje pasa la autenticación implícita o no tenía ninguna autenticación pero no se ha aplicado ninguna acción.|
   
Al mirar los encabezados de un mensaje, un administrador o incluso un usuario final puede determinar cómo Office 365 llega a la conclusión de que el remitente puede ser falso.
  
### <a name="differentiating-between-different-types-of-spoofing"></a>Diferenciar entre distintos tipos de suplantación de identidad

Microsoft diferencia entre dos tipos diferentes de mensajes de suplantación de identidad:
  
 **Suplantación interna de la organización**
  
También conocida como imitación automática, esto ocurre cuando el dominio de la dirección de: es el mismo o se alinea con el dominio del destinatario (cuando el dominio del destinatario es uno de los [dominios aceptados](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)de la organización); o bien, si el dominio de la dirección de: forma parte de la misma organización.
  
Por ejemplo, el siguiente es el remitente y el destinatario del mismo dominio (contoso.com). Los espacios se insertan en la dirección de correo electrónico para evitar la recopilación de bot en esta página):
  
De: Sender @ contoso.com
  
Para: recipient @ contoso.com
  
A continuación se indican los dominios del remitente y del destinatario que se alinean con el dominio de la organización (fabrikam.com):
  
De: Sender @ foo.fabrikam.com
  
Para: recipient @ bar.fabrikam.com
  
Los siguientes dominios de remitente y destinatario son diferentes (microsoft.com y bing.com), pero pertenecen a la misma organización (es decir, ambos forman parte de los dominios aceptados de la organización):
  
De: Sender @ microsoft.com
  
Para: recipient @ bing.com
  
Los mensajes que no superan la suplantación interna de la organización contienen los siguientes valores en los encabezados:
  
X-Forefront-antispam-rePort:... CAT: SPM/HSPM/PHSH;... SFTY: 9.11
  
El gato es la categoría del mensaje y normalmente se marca como SPM (correo no deseado), pero, en ocasiones, puede ser HSPM (correo no deseado de alta confianza) o PHISH (phishing), en función de los otros tipos de patrones que se produzcan en el mensaje.
  
SFTY es el nivel de seguridad del mensaje, el primer dígito (9) significa que el mensaje es "phishing" y el segundo conjunto de dígitos después del punto (11) significa que es la suplantación dentro de la organización.
  
No hay ningún código de motivo específico para la autenticación compuesta para la suplantación dentro de la organización, que se marcará más adelante en 2018 (escala de tiempo no definida todavía).
  
 **Suplantación de identidad entre dominios**
  
Esto ocurre cuando el dominio de envío de la dirección de: es un dominio externo a la organización receptora. Los mensajes que producen errores en la autenticación compuesta debido a la suplantación entre dominios contienen los siguientes valores en los encabezados:
  
Authentication-Results:... compauth = causa del error = 000/001
  
X-Forefront-antispam-rePort:... CAT: SUPLANTACIÓN;... SFTY: 9.22
  
En ambos casos, la siguiente sugerencia de seguridad roja se marca en el mensaje o un equivalente que se personaliza en el idioma del buzón del destinatario:
  
![Sugerencia de seguridad roja: detección de fraude](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
Es sólo mirar la dirección de: y saber qué es el correo electrónico de los destinatarios, o inspeccionar los encabezados de correo electrónico, que puede diferenciar entre la suplantación entre dominios y entre organizaciones.
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Cómo los clientes de Office 365 se pueden preparar para la nueva protección contra la suplantación de identidad

### <a name="information-for-administrators"></a>Información para los administradores

Como administrador de una organización en Office 365, hay varios datos clave que debe tener en cuenta.
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Comprender por qué la autenticación de correo electrónico no siempre es suficiente para detener la suplantación de identidad

La nueva protección contra la suplantación de identidad se basa en la autenticación de correo electrónico (SPF, DKIM y DMARC) para no marcar un mensaje como suplantación de identidad. Un ejemplo común es cuando un dominio de envío nunca ha publicado registros de SPF. Si no hay registros de SPF o no están configurados correctamente, un mensaje enviado se marcará como falso a menos que Microsoft tenga una inteligencia de servicios de fondo que diga que el mensaje es legítimo.
  
Por ejemplo, antes de que se implemente la suplantación de identidad, es posible que un mensaje se parezca a lo siguiente sin registro SPF, sin registro DKIM y sin registro de DMARC: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
Después de contraer la suplantación de identidad, si tiene Office 365 Enterprise E5, EOP o ATP, el valor de compauth se marca:
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

Si example.com corregido mediante la configuración de un registro SPF, pero no de un registro DKIM, se pasaría la autenticación compuesta porque el dominio que pasa SPF alineado con el dominio de la dirección de: 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

O bien, si configura un registro de DKIM pero no un registro de SPF, también pasaría la autenticación compuesta porque el dominio de la firma DKIM que pasó con el dominio en la dirección de:: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

Sin embargo, un phish puede también configurar SPF y DKIM, y firmar el mensaje con su propio dominio, pero especificar un dominio diferente en la dirección de:. Ni SPF ni DKIM requieren que el dominio se alinee con el dominio de la dirección de:, por lo que, a menos que example.com publicaron registros de DMARC, esto no estaría marcado como una suplantación de identidad mediante DMARC: 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

En el cliente de correo electrónico (Outlook, Outlook en la web o cualquier otro cliente de correo electrónico), solo se muestra el dominio de:, no el dominio en SPF o DKIM, y puede engañar al usuario para que piense que el mensaje procede de example.com, pero que realmente procede de maliciousDomain.com .
  
![Mensaje autenticado, pero de: el dominio no se alinea con lo que se pasa con SPF o DKIM](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
Por ese motivo, Office 365 requiere que el dominio de la dirección de: se alinee con el dominio de la firma SPF o DKIM y, de no ser así, que contenga otras señales internas que indiquen que el mensaje es legítimo. De lo contrario, el mensaje sería un error de compauth. 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

Por lo tanto, la suplantación de identidad de Office 365 protege contra dominios sin autenticación y contra dominios que configuran la autenticación pero que no coinciden con el dominio en la dirección de: que el usuario ve y cree que es el remitente del mensaje. Esto es verdadero para los dominios externos a su organización, así como para los dominios de la organización.
  
Por lo tanto, si alguna vez recibe un mensaje en el que se ha producido un error en la autenticación compuesta y se marca como suplantado, aunque el mensaje haya pasado SPF y DKIM, es porque el dominio que pasó SPF y DKIM no están alineados con el dominio de la dirección de:.
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>Descripción de los cambios en el tratamiento de los correos electrónicos falsos

Actualmente, para todas las organizaciones de Office 365-ATP y no ATP-los mensajes que producen errores de DMARC con una directiva de rechazo o cuarentena se marcan como correo no deseado y normalmente toman la acción de correo no deseado de alta confianza, o a veces, la acción normal de correo no deseado (dependiendo de si otro correo no deseado las reglas primero la identifican como correo no deseado). Las detecciones de suplantación de identidad dentro de la organización toman la acción normal de correo no deseado. No es necesario habilitar este comportamiento, ni se puede deshabilitar.
  
Sin embargo, en el caso de los mensajes de suplantación de identidad entre dominios, antes de este cambio, el correo electrónico se realizará mediante comprobaciones de correo electrónico no deseado, phish y malware, y si otras partes del filtro las identificaron como sospechosas, las marcaría como correo no deseado, phish o malware respectivamente. Con la nueva protección entre dominios de suplantación de identidad, cualquier mensaje que no se pueda autenticar, de forma predeterminada, llevará a cabo la acción \> definida en la Directiva contra la suplantación de identidad (phishing). Si no se define ninguna, se moverá a la carpeta de correo electrónico no deseado de los usuarios. En algunos casos, más mensajes sospechosos también se agregará la sugerencia de seguridad roja al mensaje.
  
Esto puede dar como resultado que algunos mensajes que se marcaron previamente como correo no deseado todavía se marquen como correo no deseado, pero ahora tendrán una sugerencia de seguridad roja; en otros casos, los mensajes que se marcaron anteriormente como correo no deseado se iniciarán marcados como correo no deseado (CAT: suPLANTAción) con una sugerencia de seguridad roja agregada. En otros casos, los clientes que han movido todo el correo no deseado y phish a la cuarentena ahora verán que van a la carpeta de correo no deseado (este comportamiento puede cambiarse, vea [cambiar la configuración contra la suplantación de identidad](#changing-your-anti-spoofing-settings)).
  
Hay varias maneras diferentes en las que se puede suplantar un mensaje (vea [diferenciar entre distintos tipos de](#differentiating-between-different-types-of-spoofing) suplantación de identidad anteriormente en este artículo), pero a partir de marzo de 2018 la forma en que Office 365 trata estos mensajes todavía no está unificada. La siguiente tabla es un resumen rápido, con una protección de suplantación entre dominios que tiene un comportamiento nuevo: 
  
|**Tipo de suplantación de identidad**|**Categoría**|**Se agregó la sugerencia de seguridad?**|**Se aplica a**|
|:-----|:-----|:-----|:-----|
|Error de DMARC (cuarentena o rechazo)  <br/> |HSPM (valor predeterminado), también puede ser SPM o PHSH  <br/> |No (aún no)  <br/> |Todos los clientes de Office 365, Outlook.com  <br/> |
|De Self a self  <br/> |SPM  <br/> |Sí  <br/> |Todas las organizaciones de Office 365, Outlook.com  <br/> |
|Entre dominios  <br/> |SUPLANTACIÓN  <br/> |Sí  <br/> |Office 365 protección contra amenazas avanzada y clientes de E5  <br/> |

### <a name="changing-your-anti-spoofing-settings"></a>Cambio de la configuración contra la suplantación de identidad

Para crear o actualizar la configuración contra la suplantación de identidad (entre dominios), navegue hasta la configuración \> de antiphishing contra la suplantación de \> identidad en la pestaña directiva &amp; de administración de amenazas del centro de seguridad y cumplimiento. Si nunca ha creado ninguna configuración antiphishing, tendrá que crear una:
  
![Anti-phishing: crear una directiva nueva](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
Si ya ha creado una, puede seleccionarla para modificarla:
  
![Anti-phishing: modificar directiva existente](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
Seleccione la Directiva que acaba de crear y continúe con los pasos descritos en [más información sobre inteligencia de](learn-about-spoof-intelligence.md)suplantación de identidad.
  
![Habilitar o deshabilitar la suplantación de identidad (phishing)](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
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

A continuación, puede modificar los parámetros de la Directiva antiphishing con PowerShell, siguiendo la documentación que se encuentra en [set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps). Puede especificar la $name como parámetro:
  
```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

Más adelante en 2018, en lugar de tener que crear una directiva predeterminada, se creará una para el ámbito de todos los destinatarios de la organización, de modo que no tenga que especificarla manualmente (las capturas de pantallas siguientes están sujetas a cambios antes de la implementación final).
  
![Directiva predeterminada para anti-phishing](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
A diferencia de una directiva que se crea, no se puede eliminar la directiva predeterminada, modificar su prioridad o elegir los usuarios, dominios o grupos a los que se va a asignar el ámbito.
  
![Detalles de la directiva predeterminada contra la suplantación de identidad](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
Para configurar la protección predeterminada con PowerShell:
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

Solo debe deshabilitar la protección contra la suplantación de identidad (antifalsificación) si tiene otros servidores de correo o servidores delante de Office 365 (consulte casos legítimos para deshabilitar la suplantación de identidad (phishing) para obtener más información).
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> Si el primer salto de la ruta de acceso de su correo electrónico es Office 365 y recibe demasiados mensajes de correo electrónico legítimo marcados como suplantación de identidad, primero debe configurar los remitentes que pueden enviar correos electrónicos falsos a su dominio (consulte la sección *"administrar los remitentes legítimos que envían u correo electrónico de nauthenticated "* ). Si sigue recibiendo demasiados falsos positivos (es decir, mensajes legítimos marcados como falso), no se recomienda deshabilitar la protección contra la suplantación de identidad. En su lugar, se recomienda elegir básica en lugar de alta protección. Es mejor trabajar con falsos positivos que exponer la organización a correo electrónico falsificado que podría acabar imponiendo costos significativamente mayores a largo plazo.

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>Administración de remitentes legítimos que envían correo electrónico no autenticado

Office 365 realiza un seguimiento de quién envía correo electrónico no autenticado a su organización. Si el servicio considera que el remitente no es legítimo, lo marcará como un error de *compauth* . Esto se clasificará como SIMULAdo, aunque depende de la Directiva contra la suplantación de identidad que se aplicó al mensaje.
  
Sin embargo, como administrador, puede especificar los remitentes a los que se les permite enviar correo electrónico falso, lo que invalida la decisión de Office 365.
  
**Método 1: Si la organización posee el dominio, configurar la autenticación de correo electrónico**
  
Este método se puede usar para resolver la suplantación de identidad dentro de la organización y la suplantación de identidad entre dominios en los casos en que se posee o interactúa con varios inquilinos. También ayuda a resolver la suplantación de identidad entre dominios donde se envía a otros clientes dentro de Office 365 y también a terceros que se hospedan en otros proveedores.
  
Para obtener más información, vea [clientes de Office 365](#customers-of-office-365).

**Método 2: usar inteligencia simulada para configurar remitentes permitidos de correo electrónico no autenticado**
  
También puede usar [inteligencia simulada](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) para permitir que los remitentes transmitan mensajes sin autenticar a su organización. 
  
Para los dominios externos, el usuario suplantado es el dominio de la dirección de, mientras que la infraestructura de envío es la dirección IP de envío (dividida en/24 intervalos de CIDR) o el dominio de la organización del registro PTR (en la captura de pantalla siguiente, es posible que la IP de envío sea 131.107.18.4 cuyo registro PTR sea outbound.mail.protection.outlook.com y se mostraría como outlook.com para la infraestructura de envío).
  
Para permitir que este remitente envíe correo electrónico no autenticado, cambie el **no** a **sí**.
  
![Configuración de los remitentes permitidos contra la suplantación de identidad](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
También puede usar PowerShell para permitir que el remitente específico suplante su dominio:
  
```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Obtención de remitentes suplantados de PowerShell](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
En la imagen anterior, se han agregado saltos de línea adicionales para que esta captura de pantalla quepa. Normalmente, todos los valores aparecen en una sola línea.
  
Edite el archivo y busque la línea correspondiente a outlook.com y bing.com, y cambie la entrada AllowedToSpoof de no a sí:
  
![Establecer falso permitir en sí en PowerShell](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
Guarde el archivo y, a continuación, ejecute:
  
```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

Ahora se permitirá a bing.com enviar correo no autenticado desde \*. Outlook.com.

**Método 3: crear una entrada de permiso para el par de remitentes/destinatarios**
  
También puede optar por omitir todo el filtrado de correo no deseado para un remitente en particular. Para obtener más información, vea [Cómo agregar de forma segura un remitente a una lista de permitidos en Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).
  
Si usa este método, se omitirá el correo no deseado y algunos de los filtros de Phish, pero no el filtrado de malware.
  
**Método 4: póngase en contacto con el remitente y pídale que configure la autenticación de correo electrónico**
  
Debido al problema de correo no deseado y suplantación de identidad (phishing), Microsoft recomienda a todos los remitentes configurar la autenticación de correo electrónico. Si conoce a un administrador del dominio de envío, póngase en contacto con él y pídale que configure los registros de autenticación de correo electrónico para que no tenga que agregar reemplazos. Para obtener más información, vea [administradores de dominios que no son clientes de Office 365](#administrators-of-domains-that-are-not-office-365-customers)", más adelante en este artículo. 
  
Aunque puede resultar difícil al principio enviar dominios para autenticar, a lo largo del tiempo, a medida que más y más filtros de correo electrónico inicien correo no deseado o rechacen su correo electrónico, los hará que establezcan los registros adecuados para garantizar una mejor entrega.
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>Visualización de informes de la cantidad de mensajes que se han marcado como falseados

Una vez habilitada la Directiva contra la suplantación de identidad, puede usar la inteligencia de amenazas para obtener números alrededor del número de mensajes que se marcan como phish. Para ello, vaya al centro de seguridad &amp; y cumplimiento (SCC) en el explorador \> de administración de amenazas, establezca la vista en phish y agrupe por dominio del remitente o el estado de protección:
  
![Ver cuántos mensajes están marcados como phish](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
Puede interactuar con los distintos informes para ver cuántos se marcaron como suplantación de identidad (phishing), incluidos los mensajes marcados como SIMULAdos. Para obtener más información, vea Introducción [a la inteligencia sobre amenazas de Office 365](get-started-with-ti.md).
  
Todavía no puede dividir qué mensajes se marcaron debido a la suplantación de identidad frente a otros tipos de suplantación de identidad (suplantación de identidad general, dominio o suplantación de usuarios, etc.). Sin embargo, más adelante, podrá hacerlo a través del centro de seguridad &amp; y cumplimiento. Una vez que lo haga, puede usar este informe como punto de partida para identificar los dominios de envío que pueden ser legítimos marcados como falseados debido a errores de autenticación.
  
La siguiente captura de pantalla es una propuesta para la apariencia de estos datos, pero puede cambiarlos cuando se lancen:
  
![Ver informes de suplantación de identidad por tipo de detección](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
Para los clientes no ATP y E5, estos informes estarán disponibles más adelante en los informes de estado de protección contra amenazas (TPS), pero se retrasarán al menos 24 horas. Esta página se actualizará a medida que se integre en el &amp; centro de seguridad y cumplimiento.
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>PreDicción del número de mensajes que se marcarán como suplantación de identidad

Una vez que Office 365 actualiza la configuración para permitirle desactivar la aplicación contra la suplantación de identidad (o con una aplicación básica o alta), tendrá la posibilidad de ver cómo cambiará la disposición del mensaje en las distintas configuraciones. Es decir, si la suplantación de identidad está desActivada, podrá ver cuántos mensajes se detectarán como suPlantación de identidad si se convierte en básico; o, si es básico, podrá ver cuántos mensajes más se detectarán como suPlantación de identidad si lo convierte en alto.
  
Esta característica está actualmente en desarrollo. A medida que se definen más detalles, esta página se actualizará con capturas de pantallas del centro de seguridad y cumplimiento, y con ejemplos de PowerShell.
  
![Informe "What if" para habilitar la contra la suplantación de identidad](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![Posible experiencia de usuario para permitir a un remitente falso](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a>Descripción de cómo se combinan el correo no deseado, el phishing y las detecciones avanzadas de suplantación de identidad

Las organizaciones que usan Exchange Online, con o sin ATP, pueden especificar las acciones que se deben llevar a cabo cuando el servicio identifica mensajes como malware, correo no deseado, correo no deseado, suplantación de identidad (phishing) y masivo. Con las directivas antiphishing de ATP para los clientes de ATP y las directivas antiphishing para los clientes de EOP, y el hecho de que un mensaje puede alcanzar varios tipos de detección (por ejemplo, malware, phishing y usuario-suplantación), puede que haya cierta confusión con respecto a qué se aplica la Directiva.
  
En general, la Directiva aplicada a un mensaje se identifica en el encabezado X-Forefront-antispam-rePort en la propiedad CAT (categoría).
  
|**Prioridad**|**Normativa**|**Categoría**|**¿Dónde se administra?**|**Se aplica a**|
|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |Software  <br/> |MALW  <br/> |[Directiva de malware](configure-anti-malware-policies.md) <br/> |Todas las organizaciones  <br/> |
|segundo  <br/> |Suplantación  <br/> |PHSH  <br/> |[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) <br/> |Todas las organizaciones  <br/> |
|3  <br/> |Correo no deseado de alta confianza  <br/> |HSPM  <br/> |[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) <br/> |Todas las organizaciones  <br/> |
|4  <br/> |Spoofing  <br/> |SUPLANTACIÓN  <br/> |[Directiva contra la](https://go.microsoft.com/fwlink/?linkid=864553)suplantación de identidad, [inteligencia](learn-about-spoof-intelligence.md) de suplantación <br/> |Todas las organizaciones  <br/> |
|2,5  <br/> |Correo no deseado  <br/> |SPM  <br/> |[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) <br/> |Todas las organizaciones  <br/> |
|6,5  <br/> |Masiva  <br/> |MASIVA  <br/> |[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) <br/> |Todas las organizaciones  <br/> |
|0,7  <br/> |Suplantación de dominio  <br/> |DIMP  <br/> |[Configurar las directivas antiphishing y anti-phishing de Office 365 ATP](set-up-anti-phishing-policies.md) <br/> |Organizaciones con ATP solamente  <br/> |
|8,5  <br/> |Suplantación de usuario  <br/> |UIMP  <br/> |[Configurar las directivas antiphishing y anti-phishing de Office 365 ATP](set-up-anti-phishing-policies.md) <br/> |Organizaciones con ATP solamente <br/> |

Si tiene varias directivas antiphishing distintas, se aplicará la que tenga la prioridad más alta. Por ejemplo, supongamos que tiene dos directivas:

|**Normativa**|**Prioridad**|**Suplantación de usuario o dominio**|**Contra la suplantación de identidad**|
|:-----|:-----|:-----|:-----|
|A  <br/> |1  <br/> |Activado  <br/> |Off  <br/> |
|B  <br/> |segundo  <br/> |Off  <br/> |Activado  <br/> |

Si un mensaje entra y se identifica como la suplantación de identidad y la suplantación del usuario, y el mismo conjunto de usuarios está en el ámbito de la Directiva A y la Directiva B, el mensaje se trata como una falsa pero no se aplica ninguna acción puesto que la suplantación de identidad está desactivada y la suPLANTAción de identidad (spoofing) se ejecuta en una prioridad más alta (4) que la suplantación del usuario (8).
  
Para que se apliquen otros tipos de directivas de suplantación de identidad, tendrá que ajustar la configuración de la persona a la que se aplican las distintas directivas.
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>Escenarios legítimos para deshabilitar la contra la suplantación de identidad

La suplantación de identidad protege mejor a los clientes de ataques de suplantación de identidad (phishing) y, por lo tanto, no se recomienda deshabilitar la protección contra suplantación de identidad. Al deshabilitarla, puede resolver algunos falsos positivos a corto plazo, pero a largo plazo estará expuesto a un mayor riesgo. El costo de configurar la autenticación en el lado del remitente o realizar ajustes en las directivas de suplantación de identidad (phishing) son normalmente sucesos únicos o requieren sólo un mantenimiento periódico y mínimo. Sin embargo, el costo de recuperación de un ataque de suplantación de identidad (phishing) en el que los datos se han expuesto o los activos se han puesto en peligro es mucho mayor.
  
Por este motivo, es mejor trabajar con falsos positivos contra la suplantación de identidad y deshabilitar la protección contra la suplantación de identidad.
  
Sin embargo, hay un escenario legítimo en el que se debe deshabilitar la suplantación de identidad, y es cuando hay productos de filtrado de correo adicionales en el enrutamiento de mensajes y Office 365 no es el primer salto en la ruta de acceso al correo electrónico:
  
![El registro MX del cliente no apunta a Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
El otro servidor puede ser un servidor de correo local de Exchange, un dispositivo de filtrado de correo como IronPort u otro servicio hospedado en la nube.
  
Si el registro MX del dominio del destinatario no apunta a Office 365, no es necesario deshabilitar la protección contra la suplantación de identidad porque Office 365 busca el registro MX del dominio receptor y suprime la suplantación de identidad (phishing) si apunta a otro servicio. Si no sabe si su dominio tiene otro servidor delante, puede usar un sitio web como el cuadro de herramientas MX para buscar el registro MX. Puede que diga algo parecido a lo siguiente:
  
![El registro MX indica que el dominio no apunta a Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
Este dominio tiene un registro MX que no apunta a Office 365, de modo que Office 365 no aplicaría la aplicación antiphishing.
  
Sin embargo, si el registro MX del dominio del destinatario *hace* punto a Office 365, aunque haya otro servicio delante de Office 365, debe deshabilitar la suplantación de identidad (phishing). El ejemplo más común es mediante el uso de la reescritura de destinatarios: 
  
![Diagrama de enrutamiento para reescritura de destinatarios](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
El registro MX del dominio contoso. com apunta al servidor local, mientras que el dominio @office365. el registro MX de contoso. net apunta a Office 365 porque contiene \*. Protection.Outlook.com o \*. EO.Outlook.com en el registro MX:
  
![El registro MX apunta a Office 365, por lo que es probable que recipient Rewrite](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
Asegúrese de diferenciarse cuando el registro MX de un dominio de destinatario no apunta a Office 365 y cuando ha sufrido la reescritura de un destinatario. Es importante conocer la diferencia entre estos dos casos.
  
Si no está seguro de si el dominio de destino ha sufrido o no la reescritura de destinatarios, a veces puede decirle que consulte los encabezados del mensaje.
  
a) en primer lugar, mire los encabezados en el mensaje para el dominio del destinatario en el encabezado Authentication-Results:
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

El dominio del destinatario se encuentra en el texto rojo en negrita, en este caso office365.contoso.net. Esto puede ser diferente que el destinatario del encabezado para:
  
Para: ejemplo de \<destinatario de destinatario @ contoso.com\>
  
Realice una búsqueda de registro MX del dominio de destinatario real. Si contiene \*. protection.outlook.com, mail.Messaging.Microsoft.com, \*. EO.Outlook.com o mail.global.FRONTBRIDGE.com, significa que MX apunta a Office 365.
  
Si no contiene esos valores, significa que el MX no señala a Office 365. Una herramienta que puede usar para comprobar esto es el cuadro de herramientas MX.
  
Para este ejemplo en concreto, lo siguiente dice que contoso.com, el dominio que se parece al destinatario desde que era el encabezado to:, tiene un registro MX que apunta a un servidor local:
  
![El registro MX apunta a un servidor local](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
Sin embargo, el destinatario real es office365.contoso.net cuyo registro MX apunta a Office 365:
  
![MX apunta a Office 365, debe ser recipient Rewrite](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
Por lo tanto, es probable que este mensaje haya sufrido una reescritura de destinatarios.
  
b) segundo, asegúrese de distinguir entre los casos de uso común de reescrituras de destinatarios. Si va a volver a escribir el dominio del destinatario en \*. onmicrosoft.com, escríbalo en su lugar a \*. mail.onmicrosoft.com.
  
Una vez que haya identificado el dominio de destinatario final que se redirige detrás de otro servidor y el registro MX del dominio del destinatario apunta realmente a Office 365 (como se publicó en sus registros DNS), puede deshabilitar la suplantación de identidad (phishing).
  
Recuerde que no desea deshabilitar la suplantación de identidad si el primer salto del dominio en la ruta de enrutamiento es Office 365, solo cuando está detrás de uno o más servicios.
  
### <a name="how-to-disable-anti-spoofing"></a>Cómo deshabilitar la suplantación de identidad (phishing)

Si ya se ha creado una directiva contra suplantación de identidad, establezca el parámetro EnableAntispoofEnforcement en $false:
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

Si no conoce el nombre de la Directiva (o las directivas) que debe deshabilitar, puede mostrarlas:
  
```
Get-AntiphishPolicy | fl Name
```

Si no tiene ninguna directiva antiphishing existente, puede crear una y, a continuación, deshabilitarla (incluso si no tiene una directiva, no se aplica la suplantación de identidad; más adelante en 2018, se creará una directiva predeterminada y, a continuación, puede deshabilitarla en lugar de crear una) . Tendrá que hacerlo en varios pasos:
  
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

La desHabilitación de la suplantación de identidad solo está disponible mediante cmdlet (más adelante estará &amp; disponible en el centro de seguridad y cumplimiento). Si no tiene acceso a PowerShell, cree un vale de soporte técnico.
  
Recuerde que esto solo debe aplicarse a dominios que sufran un enrutamiento indirecto cuando se envíen a Office 365. Resista la tentación de deshabilitar la suplantación de identidad (phishing) debido a algunos falsos positivos, será mejor en el largo plazo para trabajar con ellos.
  
### <a name="information-for-individual-users"></a>Información para usuarios individuales

Los usuarios individuales están limitados en cómo pueden interactuar con la sugerencia de seguridad contra la suplantación de identidad. Sin embargo, hay varias cosas que puede hacer para resolver escenarios comunes.
  
### <a name="common-scenario-1---mailbox-forwarding"></a>Escenario común #1: reenvío de buzones

Si usa otro servicio de correo electrónico y reenvía el correo electrónico a Office 365 o Outlook.com, su correo electrónico puede marcarse como imitación y recibir una sugerencia de seguridad roja. Office 365 y Outlook.com planean solucionar esto automáticamente cuando el reenviador es uno de Outlook.com, Office 365, Gmail o cualquier otro servicio que use el [Protocolo Arc](https://arc-spec.org). Sin embargo, hasta que se implemente la revisión, los usuarios deben usar la característica cuentas conectadas para importar sus mensajes directamente, en lugar de usar la opción de reenvío.
  
Para configurar cuentas conectadas en Office 365, seleccione el icono de engranaje en la esquina superior derecha \> de las cuentas \> \> \> conectaDas de la interfaz Web de correo de Office 365.
  
![Office 365: opción de cuentas conectadas](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
En Outlook.com, el proceso \> son las opciones \> de iconos de \> engranaje \> cuentas de correo electrónico cuentas conectadas.
  
### <a name="common-scenario-2---discussion-lists"></a>Escenario común #2 listas de discusión

Se sabe que las listas de discusión tienen problemas con la suplantación de identidad debido a la forma en que reenvían el mensaje y modifican su contenido, pero conservan el original de: Address.
  
Por ejemplo, supongamos que su dirección de correo electrónico es el usuario @ contoso.com, y que está interesado en estar en seguimiento y unirse a la lista de discusión Birdwatchers @ example.com. Cuando envíe un mensaje a la lista de discusión, puede enviarlo de esta manera:
  
**De:** Usuario de \<John Doe @ contoso.com\> 
  
**Para:** Birdwatcher de la lista \<de discusión de birdwatchers @ example.com\> 
  
**Asunto:** Excelente visualización de Jays azul en la parte superior de Mt. Rainier esta semana 
  
Cualquiera que quiera consultar la vista de esta semana desde MT. Rainier?
  
Cuando la lista de correo electrónico recibe el mensaje, da formato al mensaje, modifica su contenido y lo reproduce al resto de los miembros de la lista de discusión que está formado por participantes de muchos de los distintos receptores de correo electrónico.
  
**De:** Usuario de \<John Doe @ contoso.com\> 
  
**Para:** Birdwatcher de la lista \<de discusión de birdwatchers @ example.com\> 
  
**Asunto:** [BIRDWATCHERS] Excelente visualización de Jays azul en la parte superior de Mt. Rainier esta semana 
  
Cualquiera que quiera consultar la vista de esta semana desde MT. Rainier?
  
---
  
Este mensaje se envió a la lista de discusión Birdwatchers. Puede cancelar la suscripción en cualquier momento.
  
En el anterior, el mensaje reproducido tiene el mismo origen: Address (user @ contoso.com), pero se ha modificado el mensaje original agregando una etiqueta a la línea de asunto y un pie de página en la parte inferior del mensaje. Este tipo de modificación de mensajes es común en las listas de correo y puede dar como resultado falsos positivos.
  
Si usted o alguien de su organización es un administrador de la lista de distribución de correo, es posible que pueda configurarlo para que pase las comprobaciones contra la suplantación de identidad.
  
- Consulte las preguntas más frecuentes en DMARC.org: [he operado una lista de correo y quiero interoperar con DMARC, ¿qué debo hacer?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)

- Lea las instrucciones de esta entrada de blog: [sugerencia para operadores de listas de distribución de correo para interoperar con DMARC para evitar errores](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)

- Considere la posibilidad de instalar actualizaciones en el servidor de la lista de distribución de correo para admitir ARC, vea[https://arc-spec.org](https://arc-spec.org/)

Si no tiene la propiedad de la lista de distribución de correo:
  
- Puede solicitar al encargado de mantenimiento de la lista de distribución que implemente una de las opciones anteriores (también deben tener la autenticación de correo electrónico configurada para el dominio desde el que se retransmite la lista de correo)

- Puede crear reglas de buzón en su cliente de correo electrónico para mover mensajes a la bandeja de entrada. También puede solicitar a los administradores de su organización que configuren reglas de permiso o reemplazos, tal como se describe en la sección Administración de remitentes legítimos que envían correo no autenticado

- Puede crear un vale de soporte técnico con Office 365 para crear una invalidación de la lista de correo para tratarla como legítima

### <a name="other-scenarios"></a>Otros escenarios

1. Si ninguno de los escenarios comunes anteriores se aplica a su situación, informe del mensaje como falso positivo a Microsoft. Para obtener más información, consulte la sección [¿Cómo puedo informar a Microsoft sobre los mensajes de correo no deseado o de correo no deseado?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) más adelante en este artículo. 

2. También puede ponerse en contacto con su administrador de correo electrónico que puede aumentarlo como un tíquet de soporte técnico de Microsoft. El equipo de ingeniería de Microsoft investigará por qué el mensaje se marcó como falso.

3. Además, si sabe quién es el remitente y está seguro de que no se ha falseado de forma malintencionada, puede responder al remitente que indica que está enviando mensajes desde un servidor de correo que no se autentica. En ocasiones, esto provoca que el remitente original se ponga en contacto con su administrador de TI para configurar los registros de autenticación de correo electrónico necesarios.
  
Cuando hay suficientes remitentes que responden a los propietarios de dominio de que deben configurar los registros de autenticación de correo electrónico, se los revierten a emprender acciones. Aunque Microsoft también trabaja con los propietarios de dominios para publicar los registros necesarios, ayuda incluso más cuando los usuarios individuales lo solicitan.

4. Opcionalmente, agregue el remitente a la lista de remitentes seguros. Sin embargo, tenga en cuenta que si un phish imita la cuenta, se entregará en su buzón de correo. Por lo tanto, esta opción debe usarse con moderación.

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>Cómo deben prepararse los remitentes a Microsoft para la protección contra la suplantación de identidad

Si es un administrador que actualmente envía mensajes a Microsoft, tanto en Office 365 como en Outlook.com, debe asegurarse de que el correo electrónico se ha autenticado correctamente; de lo contrario, se puede marcar como correo no deseado o phish.
  
### <a name="customers-of-office-365"></a>Clientes de Office 365

Si es un cliente de Office 365 y usa Office 365 para enviar correo electrónico saliente:
  
- Para sus dominios, [Configure SPF en Office 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- Para los dominios principales, [use DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md)

- [Considere la posibilidad de configurar registros de DMARC](use-dmarc-to-validate-email.md) para el dominio para determinar quiénes son los remitentes legítimos

Microsoft no proporciona instrucciones de implementación detalladas para cada uno de los SPF, DKIM y DMARC. Sin embargo, hay mucha información publicada en línea. También hay compañías de terceros dedicadas a ayudar a su organización a configurar los registros de autenticación de correo electrónico.
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>Administradores de dominios que no son clientes de Office 365

Si es administrador de dominio pero no es un cliente de Office 365:
  
- Debe configurar SPF para publicar las direcciones IP de envío del dominio y también configurar DKIM (si está disponible) para firmar digitalmente los mensajes. También puede considerar la configuración de registros de DMARC.

- Si tiene remitentes en masa que transmiten correo electrónico en su nombre, debe trabajar con ellos para enviar correo electrónico de forma tal que el dominio de envío de la dirección de: (si pertenece a usted) se alinee con el dominio que pasa SPF o DMARC.

- Si tiene servidores de correo locales, o envía desde un proveedor de software como servicio, o desde un servicio de hospedaje en la nube como Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services o similar, debe asegurarse de que se agregan a su registro de SPF.

- Si es un dominio pequeño hospedado por un ISP, debe configurar su registro de SPF de acuerdo con las instrucciones que le proporcione su ISP. La mayoría de los ISP proporcionan estos tipos de instrucciones y se pueden encontrar en las páginas de soporte técnico de la compañía.

- Incluso si no ha tenido que publicar registros de autenticación de correo electrónico antes y ha funcionado bien, debe seguir publicando registros de autenticación de correo electrónico para enviar a Microsoft. Al hacerlo, le ayudará a luchar contra el phishing y reducirá la posibilidad de que usted u organizaciones a las que usted les envíe se produzcan phish.

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>¿Qué ocurre si no sabe quién envía el correo electrónico como su dominio?

Muchos dominios no publican registros de SPF porque no saben quién son todos sus remitentes. Eso no es necesario para saber quiénes son todos ellos. En su lugar, debe empezar por publicar un registro SPF para los que conoce, sobre todo donde se encuentra el tráfico corporativo, y publicar una directiva de SPF neutro, todos:
  
example.com en TXT "v = spf1 include include SPF. example. com? All"
  
La Directiva de SPF neutral significa que cualquier correo electrónico que salga de su infraestructura corporativa pasará la autenticación de correo electrónico en el resto de los receptores de correo electrónico. El correo electrónico procedente de remitentes que no conozcas se revertirá a neutro, que es prácticamente igual a no publicar ningún registro SPF.
  
Cuando se envía a Office 365, el correo electrónico que proviene del tráfico corporativo se marca como autenticado, pero el correo electrónico que proviene de las fuentes que no conoce se puede marcar como falso (en función de si Office 365 puede autenticarlo implícitamente). Sin embargo, esto sigue siendo una mejora de todo el correo electrónico que se marca como falseado por Office 365.
  
Una vez que haya empezado con un registro de SPF con una directiva de reserva de? All, puede incluir gradualmente más y más infraestructura de envío y, después, publicar una directiva más rigurosa. 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>¿Qué ocurre si es el propietario de una lista de distribución de correo?

Consulte la sección [Common scenario #2: listas de discusión](#common-scenario-2---discussion-lists).
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>¿Qué sucede si es un proveedor de infraestructura como un proveedor de servicios de Internet (ISP), un proveedor de servicios de correo electrónico (ESP) o un servicio de hospedaje en la nube?

Si hospeda el correo electrónico de un dominio y envía correo electrónico, o proporciona una infraestructura de hospedaje que pueda enviar correo electrónico, debe hacer lo siguiente:
  
- Asegurarse de que los clientes tienen documentación en la que se detalla lo que se va a publicar en sus registros de SPF

- Considere la posibilidad de firmar las firmas de DKIM en el correo electrónico saliente incluso si el cliente no lo configura de forma explícita (inicie sesión con un dominio predeterminado). Incluso puede firmar de dos veces el correo electrónico con firmas de DKIM (una vez con el dominio del cliente si lo ha configurado y una segunda vez con la firma DKIM de la compañía).

No se garantiza la entrega a Microsoft, aunque se autentique el correo electrónico procedente de la plataforma, pero al menos se asegura de que Microsoft no es correo no deseado porque no está autenticado. Para obtener más información acerca de cómo Outlook.com filtra el correo electrónico, consulte la [Página de Outlook.com postmaster](https://postmaster.live.com/pm/postmaster.aspx).
  
Para obtener más información sobre las prácticas recomendadas de los proveedores de servicios, vea [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).
  
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="why-is-microsoft-making-this-change"></a>¿Por qué Microsoft realiza este cambio?

Debido al impacto de los ataques de suplantación de identidad (phishing) y debido a que la autenticación de correo electrónico ha estado por encima de los 15 años, Microsoft cree que el riesgo de seguir permitiendo el correo electrónico no autenticado es mayor que el riesgo de perder el correo electrónico legítimo.
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>¿Este cambio hará que el correo electrónico legítimo se marque como correo no deseado?

En primer lugar, habrá algunos mensajes marcados como correo no deseado. Sin embargo, con el tiempo, los remitentes se ajustarán y, a continuación, la cantidad de mensajes que estén mal etiquetados como simulados será despreciable para la mayoría de las rutas de correo electrónico.
  
Por sí mismo, Microsoft ha adoptado esta característica varias semanas antes de implementarla en el resto de sus clientes. Mientras se producía una interrupción en primer lugar, disminuyó gradualmente.
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>¿Microsoft ofrecerá esta característica a los clientes de Outlook.com y no de la protección contra amenazas avanzada de Office 365?

La tecnología contra la suplantación de identidad de Microsoft se implementó inicialmente en sus organizaciones con una suscripción a Office 365 Enterprise E5 o compró el complemento de protección contra amenazas avanzada (ATP) de Office 365 para su suscripción. A partir de octubre, 2018 hemos ampliado la protección a las organizaciones que también tienen Exchange Online Protection (EOP). En el futuro, podemos liberarla para Outlook.com. Sin embargo, si lo hacemos, es posible que haya algunas funcionalidades que no se aplican, como la creación de informes y reemplazos personalizados.
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>¿Cómo puedo informar a Microsoft de los mensajes de correo no deseado o de correo no deseado?

Puede usar el complemento de [mensajes de informe para Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)o, si no está instalado, enviar mensajes de correo no deseado, de correo [no deseado o de suplantación de identidad a Microsoft para su análisis](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx).
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>Soy Administrador de dominio que no sabe quién es el propietario de mis remitentes.

Consulte [administradores de dominios que no son clientes de Office 365](#administrators-of-domains-that-are-not-office-365-customers).
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>¿Qué sucede si se deshabilita la protección contra la suplantación de identidad para mi organización, aunque Office 365 sea el filtro principal?

No se recomienda porque se expondrá a más mensajes de suplantación de identidad (phishing) y correo no deseado. No todos los suplantadores de identidad están suplantando, y no se pierden todas las suplantaciones de identidad. Sin embargo, el riesgo será mayor que el de un cliente que habilite la suplantación de identidad.
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>¿La protección contra la suplantación de identidad (phishing) significa que estoy protegido contra la suplantación de identidad (phishing)?

Desafortunadamente, no, ya que los phishers se adaptarán a usar otras técnicas como cuentas comprometidas o configurar cuentas de servicios gratuitos. Sin embargo, la protección contra la suplantación de identidad funciona mucho mejor para detectar estos otros tipos de métodos de suplantación de identidad porque las capas de protección de Office 365 están diseñadas y se crean de forma conjunta.
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>¿Otros receptores de correo electrónico grandes bloquean el correo electrónico no autenticado?

Casi todos los receptores de correo de gran tamaño implementan SPF tradicional, DKIM y DMARC. Algunos receptores tienen otras comprobaciones que son más estrictas que solo esos estándares, pero pocos van hasta el momento en que Office 365 bloquea el correo no autenticado y los trata como una falsificación. Sin embargo, la mayor parte de la industria es cada vez más estricta con respecto a este tipo de correo electrónico en particular, en especial debido al problema de la suplantación de identidad.
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>¿Todavía necesito la opción de filtrado de correo no deseado avanzado habilitada para "error de errores de SPF" si habilito la suplantación de identidad (phishing)?

No, esta opción ya no es necesaria porque la característica contra la suplantación de identidad no solo considera un error grave de SPF, sino un conjunto mucho más amplio de criterios. Si tiene habilitada la opción contra la suplantación de identidad y se ha habilitado la opción error en disco SPF, probablemente obtendrá más falsos positivos. Le recomendamos que deshabilite esta característica ya que no proporcionará más capturas para correo no deseado o phish, sino que generará principalmente falsos positivos.
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>¿Ayuda el esquema de reescritura de remitentes (SRS) para corregir el correo reenviado?

SRS solo corrige parcialmente el problema del correo electrónico reenviado. Al volver a escribir el correo SMTP desde, SRS puede asegurarse de que el mensaje reenviado pasa SPF en el siguiente destino. Sin embargo, dado que la suplantación de identidad se basa en la dirección de: en combinación con el dominio de firma de correo electrónico o de firma DKIM (u otras señales), no es suficiente evitar que el correo electrónico reenviado se marque como falseado.