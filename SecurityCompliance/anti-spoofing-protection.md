---
title: Protección contra suplantación de identidad en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
description: Este artículo describe cómo Office 365 mitiga frente a ataques de suplantación de identidad que usa falsificado dominios de remitente, es decir, los dominios que están suplantados. Para ello, mediante el análisis de los mensajes y bloqueo de las que pueden ser autenticados neithe mediante el uso de métodos de autenticación de correo electrónico estándar, ni otras técnicas de reputación del remitente. Este cambio se que se implementa para reducir el número de ataques de suplantación de identidad se exponen las organizaciones en Office 365 a.
ms.openlocfilehash: bbcfbcdf32c87e070f10c9478a7c5978e909f009
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22559225"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Protección contra suplantación de identidad en Office 365

Este artículo describe cómo Office 365 mitiga frente a ataques de suplantación de identidad que usa falsificado dominios de remitente, es decir, los dominios que están suplantados. Para ello, analizar los mensajes y el bloqueo de los que no se puede autenticar mediante los métodos de autenticación de correo electrónico estándar, ni otras técnicas de reputación del remitente. Este cambio se que se implementa para reducir el número de ataques de suplantación de identidad se exponen a los clientes a.
  
En este artículo también se describe por qué se está realizando este cambio, cómo pueden preparar los clientes para que este cambio, cómo ver los mensajes que se verán afectados, cómo informar sobre los mensajes, cómo mitigar falsos positivos, así como cómo deben preparar los remitentes a Microsoft para esto cambiar.
  
La tecnología de Microsoft contra la suplantación se implementa inicialmente en su protección de amenaza avanzada de Office 365 (ATP) y los clientes E5. Sin embargo, debido a la forma en que todos sus filtros de información sobre cada uno de los otros, incluso los usuarios de Outlook.com y los clientes que no sean ATP pueden también verse afectados.
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Cómo se utiliza la suplantación de identidad en los ataques de suplantación de identidad

En cuanto a la protección de sus usuarios, Microsoft toma en serio la amenaza de suplantación de identidad. Una de las técnicas que normalmente usan los remitentes de spam y los suplantadores de identidad es suplantación de identidad, que es cuando el remitente está falsificado, y aparece un mensaje que proceden de una persona o en cualquier lugar que no sea el origen real. Esta técnica se usa a menudo en las campañas de suplantación de identidad diseñadas para obtener las credenciales de usuario. Tecnología de protección contra suplantación de Microsoft específicamente examina la falsificación de la ' desde: encabezado ' que es la única que se muestra en un cliente de correo electrónico como Outlook. Cuando Microsoft dispone de alta confianza que desde: encabezado está suplantado, identifica el mensaje como una dirección falsa.
  
Los mensajes de suplantación de identidad tienen dos implicaciones negativas para los usuarios de la vida real:
  
### <a name="1-spoofed-messages-deceive-users"></a>1. falsificados mensajes engañar a los usuarios
  
En primer lugar, un mensaje falso puede engañar a un usuario para que al hacer clic en un vínculo y renunciar a sus credenciales, descarga malware o responder a un mensaje con contenido confidencial (el último de los cuales se conoce como compromiso de correo electrónico empresarial). Por ejemplo, el siguiente es un mensaje de suplantación de identidad con un remitente falsificado de msoutlook94@service.outlook.com:
  
![Mensaje de suplantación de identidad suplantación de service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
Lo anterior no proviene realmente de service.outlook.com, pero en su lugar haya sido suplantada por el atacante para facilitar la misma apariencia que. Está intentando engañar a un usuario para que al hacer clic en el vínculo dentro del mensaje.
  
El ejemplo siguiente es la falsificación de contoso.com:
  
![Mensaje de suplantación de identidad - compromiso de correo electrónico de negocio](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
El mensaje parece legítimo, pero en realidad es una dirección falsa. Este mensaje de suplantación de identidad es un tipo de compromiso de correo electrónico empresarial que es una subcategoría de suplantación de identidad.
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. los usuarios se debe confundir los mensajes reales para modificarlos falsos
  
Los mensajes en segundo lugar, falsos crean incertidumbre para los usuarios que saber acerca de los mensajes de suplantación de identidad, pero no puede saber la diferencia entre un mensaje real y uno FALSO. Por ejemplo, el siguiente es un ejemplo de una contraseña real restablecer desde la dirección de correo electrónico de la cuenta de Microsoft Security:
  
![Restablecimiento de contraseña legítima de Microsoft](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
El mensaje anterior ¿proviene de Microsoft, pero al mismo tiempo, los usuarios se utilizan para obtener los mensajes de suplantación de identidad que puede engañar a un usuario al hacer clic en un vínculo y renunciar a sus credenciales, descarga malware o responder a un mensaje con contenido confidencial. Dado que es difícil indicar la diferencia entre un restablecimiento de la contraseña real y una falsificación uno, muchos usuarios omitir estos mensajes, identificarlos como correo no deseado o innecesariamente informar de los mensajes a Microsoft como las estafas de suplantación de identidad perdidas.
    
Para detener la suplantación de identidad, el correo electrónico filtrado del sector ha desarrollado protocolos de autenticación de correo electrónico como [SPF](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx), [DKIM](https://technet.microsoft.com/en-us/library/mt695945%28v=exchg.150%29.aspx)y [DMARC](https://technet.microsoft.com/en-us/library/mt734386%28v=exchg.150%29.aspx). DMARC evita la suplantación de examen de un remitente mensaje - que el usuario ve en su cliente de correo electrónico (en los ejemplos anteriores, esto es service.outlook.com, outlook.com y accountprotection.microsoft.com) - con el dominio que se pasa SPF o DKIM. Es decir, el dominio que ve el usuario se ha autenticado y, por tanto, no se suplanta. Para obtener una descripción más completa, vea la sección " *Descripción de por qué la autenticación de correo electrónico no siempre es suficiente para detener la suplantación de identidad"* más adelante en este documento. 
  
Sin embargo, el problema es que la autenticación de correo electrónico registros son opcionales, no es necesario. Por lo tanto, mientras que los dominios con las directivas de autenticación segura, como microsoft.com y skype.com están protegidos contra suplantación de identidad, dominios que publicar las directivas de autenticación más débiles o ninguna directiva en absoluto, son el objetivo de suplantación. A partir de marzo de 2018, sólo un 9% de dominios de las compañías en la lista de Fortune 500 publicar las directivas de autenticación de correo electrónico seguro. El 91% restante puede ser suplantada por un atacante y, a menos que detecte el filtro de correo electrónico, con la directiva de otro, se puede entregar a un usuario final y engañar a ellos:
  
![Directivas de DMARC de compañías de Fortune 500](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
La proporción de las empresas de tamaño de pequeñas y medianas no son en la lista de Fortune 500 que publicar las directivas de autenticación de correo electrónico seguro es más pequeño y más pequeños aún para dominios que están fuera de Norteamérica y Europa occidental.
  
Esto es un gran problema porque mientras las empresas pueden no ser conscientes de cómo funciona la autenticación de correo electrónico, los suplantadores de identidad comprender y permite aprovechar la falta del mismo.
  
Para obtener información sobre la configuración de SPF, DKIM y DMARC, vea la sección " *a los clientes de Office 365"* más adelante en este documento. 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>Detención de suplantación de identidad con la autenticación implícita de correo electrónico

Debido a que la suplantación de identidad de suplantación de identidad y lanza es este problema y debido a la adopción de directivas de autenticación de correo electrónico seguro limitada, Microsoft continúa invirtiendo en capacidades para proteger a sus clientes. Por lo tanto, Microsoft está moviendo con antelación con *la autenticación implícita de correo electrónico* - si no autentica un dominio, Microsoft se tratará como si haya publicado registros de la autenticación de correo electrónico y tratar adecuadamente si no se pasan. 
  
Para ello, Microsoft ha creado numerosas extensiones a la autenticación de correo electrónico regular incluidos reputación del remitente, historial de remitentes/destinatarios, análisis de comportamiento y otras técnicas avanzadas. Un mensaje enviado desde un dominio que no publica la autenticación de correo electrónico se marcará como falso a menos que lo contiene otros señales indicar que es legítimo.
  
Al hacerlo, end pueden tener los usuarios con nivel de confianza que no se ha suplantado un correo electrónico enviado a ellos, los remitentes pueden estar seguros de que nadie está suplantando a su dominio, y los clientes de Office 365 pueden ofrecer protección incluso mejor como protección de suplantación.
  
Para ver el anuncio general de Microsoft, vea [un mar de phishing parte 2 - mejorado contra suplantación de identidad en Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>Identificación de que un mensaje se clasifica como suplantada

### <a name="composite-authentication"></a>Autenticación compuesta

Mientras SPF, DKIM y DMARC pueden ser todos útiles por sí mismos, no comunicar el suficiente estado de la autenticación en el caso de un mensaje no tiene autenticación explícita registros. Por lo tanto, Microsoft ha desarrollado un algoritmo que combina varias señales en un único valor que se denomina autenticación compuesto, o compauth para short. Los clientes de Office 365 tienen los valores de compauth que se mostrará en el encabezado de *Resultados de la autenticación* en los encabezados de mensaje. 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**Resultado de CompAuth**|**Descripción**|
|:-----|:-----|
|conmutación por error|Mensaje de error de autenticación explícita (envío de dominio publicado al registros explícitamente en DNS) o la autenticación implícita (envío de dominio no publica los registros de DNS, por lo que Office 365 interpolan el resultado como si lo hubiera publicado registros).|
|pase|Mensaje pasa autenticación explícita (mensaje pasa DMARC o [Procedimientos DMARC pasa adivinar](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) o la autenticación implícita con confianza alta (envío de dominio no publica los registros de la autenticación de correo electrónico, pero Office 365 tiene señales de seguro back-end indicar el mensaje es probable que legítimos).|
|softpass|Mensaje que pasa la autenticación implícita con confianza bajo a medio (envío de dominio no publica la autenticación de correo electrónico, pero Office 365 tiene señales de back-end para indicar el mensaje es legítimo pero la fuerza de la señal es más débil).|
|Ninguno|Mensaje no se autenticó (o se autenticó pero que no Alinear), pero no se aplican debido a la reputación del remitente o de otros factores de autenticación compuesta.|
   
|||
|:-----|:-----|
|**Reason**|**Descripción**|
|0XX|Mensaje de error de autenticación compuesta.<br/>**000** significa que el mensaje no pudo DMARC con una acción de rechazar o cuarentena.                    -001 significa que el mensaje de error en la autenticación implícita de correo electrónico. Esto significa que el dominio del remitente no tenía registros de la autenticación de correo electrónico publicados o, si es así, que tenían una directiva de errores más débil (fail suave SPF o neutral, directiva de DMARC de p = none).<br/>**002** significa que la organización tiene una directiva para el par de remitente o dominio que está prohibido explícitamente de envío de correo electrónico falso, esta configuración se establece manualmente por un administrador.  <br/>**010** significa que el mensaje no pudo DMARC con una acción de rechazar o cuarentena, y el dominio del remitente es uno de los dominios aceptados de su organización (Esto es parte de self-to-self o dentro de la organización, suplantación de identidad).  <br/>**011** significa que el mensaje de error en la autenticación implícita de correo electrónico y el dominio del remitente es uno de los dominios aceptados de su organización (Esto es parte de self-to-self o dentro de la organización, suplantación de identidad).|
|Todos los otros códigos (1xx, 2xx, 3xx, 4xx, 5xx)|Corresponde a diversos códigos internos de por qué un mensaje pasa a la autenticación implícita o no tenía autenticación pero no se aplicó ninguna acción.|
   
Mirando los encabezados de un mensaje, un administrador o incluso un usuario final puede determinar cómo Office 365 llega a la conclusión que el remitente puede ser suplantado.
  
### <a name="differentiating-between-different-types-of-spoofing"></a>Diferenciar los distintos tipos de suplantación de identidad

Microsoft distingue entre dos tipos diferentes de los mensajes de suplantación de identidad:
  
 **Suplantación de identidad dentro de la organización**
  
También conocido como self-to-self suplantación de identidad, esto se produce cuando el dominio en el campo de: dirección es la misma que o se alinea con el dominio de destinatario (cuando el dominio de destinatario es uno de los [Dominios aceptados](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)de su organización); o bien, cuando el dominio en el campo de: dirección es parte de la misma organización.
  
Por ejemplo, el siguiente tiene remitente y el destinatario desde el mismo dominio (contoso.com). En la dirección de correo electrónico para evitar que el robot electrónico recolección en esta página se insertan espacios):
  
De: remitente @ contoso.com
  
Para: destinatario @ contoso.com
  
El siguiente consta de los dominios de remitente y el destinatario alinear con el dominio organizativo (fabrikam.com):
  
De: remitente @ foo.fabrikam.com
  
Para: destinatario @ bar.fabrikam.com
  
Los siguientes dominios de remitente y el destinatario son diferentes (microsoft.com y bing.com), pero pertenecen a la misma organización (es decir, ambos forman parte de dominios aceptados de la organización):
  
De: remitente @ microsoft.com
  
Para: destinatario @ bing.com
  
Los mensajes que no pasan la suplantación de identidad dentro de la organización contienen los siguientes valores en los encabezados:
  
X-Forefront-Antispam-Report:... CAT:SPM/HSPM/PHSH;... SFTY:9.11
  
El gato es la categoría del mensaje y normalmente se marca como SPM (correo no deseado), pero en ocasiones pueden ser HSPM (correo no deseado de alta confianza) o phishing (suplantación de identidad) dependiendo de qué otros tipos de modelos se producen en el mensaje.
  
El SFTY es el nivel de seguridad del mensaje, el primer medio de dígito (9) del mensaje es suplantación de identidad y segundo conjunto de dígitos después del punto (11) significa que es la suplantación de identidad dentro de la organización.
  
No hay ningún código de motivo específico para la autenticación de composición para dentro de suplantación, de la organización, se mostrará más adelante en 2018 (escala de tiempo aún no se ha definido).
  
 **Suplantación de identidad entre dominios**
  
Esto se produce cuando el dominio en el campo de envío: dirección es un dominio externo a la organización receptora. Los mensajes que no pasan la autenticación compuesto debido a la suplantación de identidad entre dominios contienen los siguientes valores en los encabezados:
  
Resultados de autenticación:... compauth = fail motivo = 000/001
  
X-Forefront-Antispam-Report:... CAT:SPOOF;... SFTY:9.22
  
En ambos casos, se mostrará la sugerencia de color rojo de seguridad siguientes en el mensaje, o un equivalente que se personaliza para el idioma del buzón de destinatarios:
  
![Sugerencia de seguridad rojo - detección loterías](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
Es solo con mirar desde: de direcciones y saber cuál es su correo electrónico del destinatario o por inspeccionar los encabezados de correo electrónico, que se pueden diferenciar entre dominios de suplantación y dentro de la organización.
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Cómo los clientes de Office 365 pueden prepararse para la nueva protección contra la suplantación

### <a name="information-for-administrators"></a>Información para los administradores

Como administrador de una organización en Office 365, hay varias partes clave de la información que deben tener en cuenta.
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Descripción de por qué la autenticación de correo electrónico no siempre es suficiente para detener la suplantación de identidad

La protección contra la suplantación nuevo se basa en la autenticación de correo electrónico (SPF, DKIM y DMARC) no marcar un mensaje como suplantación de identidad. Un ejemplo común es cuando un dominio remitente nunca ha publicado los registros de SPF. Si no hay ningún registro SPF o que están configurados correctamente, se marcará un mensaje enviado como suplantar a menos que Microsoft tiene inteligencia de back-end que indica que el mensaje es legítimo.
  
Por ejemplo, antes de contra la suplantación va a implementar, un mensaje es posible que han consultado como la siguiente con ningún registro de SPF, no hay ningún registro DKIM y ningún registro DMARC: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
Después de contra la suplantación, si es usted un cliente avanzado de protección contra amenazas o E5, se mostrará el valor de compauth (los clientes que no sean de ATP y que no sean E5 no se ven afectados):
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

Si example.com fijo esto mediante la configuración de un registro SPF pero no es un registro DKIM, esto pasaría autenticación compuesta debido a que el dominio que se pasa SPF se alinea con el dominio en el campo de: dirección: 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

O bien, si ha configurado un registro DKIM pero no un registro SPF, esto también pasaría autenticación compuesta debido a que el dominio en la firma de DKIM que pasa se alinea con el dominio en el campo de: dirección: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

Sin embargo, un atacante puede también configurar SPF y DKIM y firmar el mensaje con su propio dominio, pero especificar un dominio diferente en el campo de: dirección. SPF ni DKIM requiere el dominio que se va a alinear con el dominio en el campo de: de direcciones, por lo que, a menos que example.com publicado registros DMARC, esto no está marcado como suplantación mediante DMARC: 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

En el cliente de correo electrónico (Outlook, Outlook en el web, o cualquier otro cliente de correo electrónico), sólo la From: se muestra el dominio, no en el dominio en el SPF o DKIM y que puede engañar al usuario en pensando example.com del que procede el mensaje, pero realmente procede de maliciousDomain.com .
  
![Mensaje autenticado pero desde: dominio no se alinea con la información que pasa SPF o DKIM](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
Por ese motivo, Office 365 requiere que el dominio en el campo de: dirección se alinea con el dominio en la firma de SPF o DKIM y, si no, contiene otras señales interno que indica que el mensaje es legítimo. De lo contrario, el mensaje sería un error compauth. 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

Por lo tanto, Office 365 contra la suplantación protege contra dominios sin autenticación y contra dominios que ha configurado la autenticación pero el error de coincidencia para el dominio en el campo de: direcciones ya que es el que el usuario ve y se considera que son el remitente del mensaje. Esto es así tanto de dominios externos a su organización, así como dominios dentro de la organización.
  
Por lo tanto, si alguna vez recibe un mensaje de error de autenticación compuesta y se marca como suplantada, incluso si el mensaje pasa SPF y DKIM, es debido a que el dominio que se pasa SPF y DKIM no se alinea con el dominio en el campo de: dirección.
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>Se tratan los cambios de descripción en los correos electrónicos de cómo falsos

Actualmente, todas las organizaciones de Office 365 - ATP y que no sean-ATP - mensajes que no pasan la DMARC con una directiva de rechazar o cuarentena están marcadas como correo no deseado y normalmente lleve a cabo la acción de spam de alta confianza o, a veces en la acción de spam regular (dependiendo de si otro spam las reglas en primer lugarlo identifican como correo no deseado). Detecciones de falsos dentro de la organización tomar la acción spam regular. Este comportamiento no deben habilitarse ni puede deshabilitarse.
  
Sin embargo, para los mensajes de suplantación de identidad de dominios, antes de este cambio debería conducir a través de comprobaciones de correo no deseado, phishing y malware regulares y si otras partes del filtro identifican como sospechosos, ¿marcarlos como malware, phishing o spam respectivamente. Con la protección de suplantación de identidad de dominios nuevo, los mensajes que no se puede autenticar, de forma predeterminada, realizará la acción definida en el Anti-phishing \> directiva de la suplantación de identidad. Si uno no está definida, se moverán a una carpeta de correo electrónico no deseado de los usuarios. En algunos casos, los mensajes sospechosos más también va a tener la sugerencia de seguridad rojo agrega al mensaje.
  
Esto puede resultar en algunos mensajes que se han marcado anteriormente como correo no deseado aún Introducción marcados como correo no deseado pero ahora tendrá también una sugerencia de color rojo de seguridad; en otros casos, los mensajes que anteriormente se han marcado como que no sean correo no deseado se iniciará Introducción marcados como correo no deseado (CAT:SPOOF) con una sugerencia de color rojo seguridad agregan. En algunos casos, los clientes que se han mover todos los spam y phishing a la cuarentena ahora verían va a la carpeta correo electrónico no deseado (este comportamiento se puede cambiar, vea [cambiar la configuración contra la suplantación](#changing-your-anti-spoofing-settings)).
  
Hay varias maneras diferentes de que un mensaje puede ser suplantado (vea [Differentiating entre los diferentes tipos de suplantación de identidad](#differentiating-between-different-types-of-spoofing) anteriormente en este artículo) pero a partir de marzo de 2018 no está todavía unificada la forma en que Office 365 trata estos mensajes. La tabla siguiente es un resumen rápido, con protección de suplantación de identidad de dominios que se va a nuevo comportamiento: 
  
|**Tipo de suplantación**|**Categoría**|**¿Sugerencia de seguridad agregado?**|**Se aplica a**|
|:-----|:-----|:-----|:-----|
|Error DMARC (cuarentena o rechazar)  <br/> |HSPM (valor predeterminado), también pueden ser SPM o PHSH  <br/> |No (no)  <br/> |Todos los clientes de Office 365, Outlook.com  <br/> |
|Self-to-self  <br/> |SPM  <br/> |Sí  <br/> |Todas las organizaciones de Office 365, Outlook.com  <br/> |
|Entre dominios  <br/> |SUPLANTACIÓN DE LA  <br/> |Sí  <br/> |Clientes de Office 365 avanzada protección frente a amenazas y E5  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a>Cambiar la configuración contra la suplantación

Para crear o actualizar la configuración contra la suplantación de (dominios), navegue hasta el Anti-phishing \> contra la suplantación de la configuración en la administración de amenaza \> ficha Directiva en la seguridad &amp; centro de cumplimiento. Si nunca ha creado cualquier configuración contra suplantación de identidad, debe crear uno:
  
![Contra - crear una nueva directiva](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
Si ya ha creado, se puede seleccionar para modificarla:
  
![Contra - modificar directiva existente](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
Seleccione la directiva que acaba de crear y continúe con los pasos tal como se describe en [obtener más información acerca de la suplantación de la inteligencia.](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)
  
![Habilitar o deshabilitar antispoofing](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![Habilitar o deshabilitar las sugerencias de seguridad antispoofing](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
Para crear una nueva directiva a través de PowerShell: 
  
```
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

A continuación, puede modificar los parámetros de directiva contra suplantación de identidad con PowerShell, siguiendo la documentación en [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps). Puede especificar la $name como un parámetro:
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

Más adelante en 2018, en lugar de que tener que crear una directiva predeterminada, se creará para la que se limita a todos los destinatarios de la organización para que no tenga que se especifique manualmente (las capturas de pantalla que aparece a continuación están sujetos a cambios antes de la implementación final).
  
![Directiva predeterminada para contra](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
A diferencia de una directiva que cree, no se puede eliminar la directiva predeterminada, modificar su prioridad o elegir qué usuarios, dominios o grupos para delimitar.
  
![Detalles de la directiva contra predeterminada](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
Más adelante en 2018, para configurar la protección de forma predeterminada a través de PowerShell:
  
```
$defaultAntiphishPolicy = Get-AntiphishingPolicy -IsDefault $true
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

Sólo debe deshabilitar protección contra la suplantación si tiene otro servidor de correo o servidores delante de Office 365 (vea los escenarios legítimos para deshabilitar contra suplantación de identidad para obtener más detalles). 
  
```
$defaultAntiphishPolicy = Get-AntiphishingPolicy -IsDefault $true
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> Si el primer salto en la ruta de acceso de correo electrónico es Office 365 y reciben demasiados mensajes de correo electrónico legítimos marcados como falso, primero debe configurar la lista de remitentes que tienen permiso para enviar correo electrónico simulado a su dominio (vea la sección "Managing remitentes legítimos que va a enviar u * correo electrónico nauthenticated"* ). Si aún está recibiendo demasiados falsos positivos (por ejemplo, legítimos mensajes marcados como falso), no se recomienda deshabilitar protección contra la suplantación por completo. En su lugar, se recomienda que elija básica en lugar de protección alta.                    Es mejor trabajar a través de falsos positivos que a exponer la organización para el correo electrónico simulado que puede acabar imponer significativamente mayores costes a largo plazo.

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>Administración de remitentes legítimos que va a enviar correo electrónico sin autenticar

Office 365 realiza un seguimiento de quién está enviando correo electrónico sin autenticar a su organización. Si el servicio cree que el remitente no es legítimo, marcará como un error de *compauth* . Esto se clasifica como FALSO aunque depende de la directiva contra la suplantación de que se aplicó al mensaje. 
  
Sin embargo, como administrador, puede especificar qué remitentes tienen permiso para enviar correo electrónico simulado, invalidación de decisión de Office 365.
  
**Método 1: si su organización posee el dominio, configurar la autenticación de correo electrónico**
  
Este método se puede usar para resolver entre dominios de suplantación en los casos donde propietario o interactuar con varios inquilinos y suplantación de identidad dentro de la organización. También ayuda a resolver dominios suplantación de identidad en el que enviar a otros clientes dentro de Office 365 y, también de terceros que se hospedan en otros proveedores.
  
Para obtener más información, vea [los clientes de Office 365](#customers-of-office-365). 
 
**Método 2: inteligencia de uso simulado para configurar remitentes permitidos de correo electrónico sin autenticar**
  
También puede usar la [Suplantación de la inteligencia](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) para permitir que los remitentes para transmitir mensajes no autenticados a su organización. 
  
Para dominios externos, el usuario suplantado es el dominio en la dirección, mientras que la infraestructura de envía es la dirección IP remitente (dividido en /24 rangos CIDR), o en el dominio organizativo del registro PTR (en la captura de pantalla que aparece a continuación, la dirección IP remitente es posible que ser 131.107.18.4 cuyo registro PTR es outbound.mail.protection.outlook.com, y esto se mostrará como outlook.com para la infraestructura de envía).
  
Para permitir que este remitente para enviar correo electrónico sin autenticar, cambie el **No** a **Sí**.
  
![Configuración de antispoofing remitentes permitido](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
También puede usar PowerShell para permitir que un remitente específico suplantar su dominio: 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Introducción a los remitentes falsos a través de Powershell](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
En la imagen anterior, se han agregado los saltos de línea adicionales hacer que esta captura de pantalla que se ajuste, pero en realidad, todos los valores aparecería en una sola línea.
  
Edite el archivo y busque la línea que corresponde a outlook.com y bing.com y cambie la entrada AllowedToSpoof de No a sí:
  
![Suplantación de la opción Permitir que sí a través de Powershell](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
Guarde el archivo y, a continuación, ejecute: 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

Esto le permitirá ahora bing.com enviar correo electrónico sin autenticar desde \*. outlook.com.

**Método 3: crear una entrada de permitir para el par de remitentes/destinatarios**
  
También puede elegir omitir todo el spam filtrado un remitente específico. Para obtener más información, vea [cómo agregar un remitente a una lista Permitir en Office 365 de forma segura](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).
  
Si utiliza este método, omitirá correo no deseado y algunas de filtrado de phishing, pero no el filtrado de malware.
  
**Método 4 - póngase en contacto con el remitente y pídales que configurar la autenticación de correo electrónico**
  
Debido al problema de correo no deseado y suplantación de identidad, Microsoft recomienda configurar la autenticación de correo electrónico de todos los remitentes. Si sabe que un administrador del dominio envío, póngase en contacto con ellos y solicitud que configuración los registros de la autenticación de correo electrónico para que no tenga que agregar cualquier reemplazos. Para obtener más información, vea [los administradores de dominios que son no los clientes de Office 365](#administrators-of-domains-that-are-not-office-365-customers)"más adelante en este artículo. 
  
Aunque puede ser difícil en primer lugar obtener envío de dominios para autenticar, con el tiempo, como más filtros de correo electrónico iniciar junking o incluso rechazar su correo electrónico, lo harán configurar los registros adecuados para garantizar la entrega mejor.
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>Visualización de informes de cuántos mensajes se han marcado como suplantada

Una vez que la directiva contra la suplantación está habilitada, puede usar información sobre amenazas para obtener números de alrededor de la cantidad de mensajes se marca como phishing. Para ello, vaya a la seguridad &amp; centro de cumplimiento (SCC) en administración de amenaza \> Explorer, establecer la vista para phishing y grupo mediante el dominio del remitente o el estado de protección:
  
![Ver el número de mensajes se marca como phishing](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
Puede interactuar con los diversos informes para ver cuántas se han marcado como suplantación de identidad, incluidos los mensajes marcados como falso. Para obtener más información, vea [Introducción a Office 365 amenaza inteligencia](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441).
  
Aún no se puede dividir la salida que se han marcado los mensajes debido a la suplantación de identidad frente a otros tipos de suplantación de identidad (phishing general, suplantación de dominio o usuario y así sucesivamente). Sin embargo, más adelante en 2018, podrá hacerlo a través de la seguridad &amp; centro de cumplimiento. Una vez que lo hace, puede usar este informe como punto de partida para identificar dominios envío que pueden ser legítimos que se están marcados como falso debido a error de autenticación.
  
La siguiente captura de pantalla es una propuesta de cómo buscará estos datos, pero pueden cambiar al soltar:
  
![Visualización de informes de suplantación de identidad por tipo de detección](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
Para que no sean de ATP y los clientes E5, estos informes estarán disponibles más adelante en 2018 debajo de los informes de estado de protección de amenaza (TPS), pero se retrasarán por al menos 24 horas. Esta página se actualizará cuando se integran en la seguridad &amp; centro de cumplimiento.
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>Predecir cuántos mensajes se marcarán como falso

Más adelante en 2018, una vez Office 365 actualiza su configuración para permitir que desactivar el cumplimiento contra la suplantación o en con la aplicación de Basic o alta, se le ofrecerá la posibilidad de ver cómo cambia en las diferentes opciones de eliminación de mensaje. Es decir, si contra la suplantación está desactivada, podrá ver cuántos mensajes se detectarán como falso si activar a Basic; o bien, si es Basic, podrá ver cuántos mensajes más se detectarán como falso si activa a alta.
  
Esta característica está actualmente en desarrollo. Tal y como se definen más detalles, esta página se actualizará con capturas de pantalla de la seguridad y el centro de cumplimiento tanto con ejemplos de PowerShell.
  
!["¿Qué ocurre si" informe para habilitar antispoofing](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![Experiencia de usuario posible para permitir a un remitente falso](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a>Comprender cómo contra correo no deseado, suplantación de identidad y suplantación de identidad avanzada se combinan las detecciones

Los clientes de Exchange Online - ATP y que no sean ATP - son capaces de especificar las acciones que se realizarán cuando el servicio identifica los mensajes como malware, correo no deseado, spam de alta confianza, suplantación de identidad y masiva. Sin embargo, con la introducción de nuevas directivas contra suplantación de identidad para los clientes de ATP y el hecho de que un mensaje puede alcanzado a varios tipos de detección (por ejemplo, malware, suplantación de identidad y suplantación de usuario), puede haber confusión acerca de qué se aplica la directiva. 
  
En general, la directiva aplicada a un mensaje se identifica en el encabezado X-Forefront-Antispam-Report en la propiedad CAT (categoría). 
  
|**Priority**|**Directiva**|**Categoría**|**¿Donde administradas?**|**Se aplica a**|
|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |Malware  <br/> |MALW  <br/> |[Directiva de malware](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |Todos los clientes  <br/> |
|2  <br/> |Suplantación de identidad  <br/> |PHSH  <br/> |[Directiva de filtro de contenido hospedado](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Todos los clientes  <br/> |
|3  <br/> |Correo no deseado de alta confianza  <br/> |HSPM  <br/> |[Directiva de filtro de contenido hospedado](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Todos los clientes  <br/> |
|4  <br/> |Suplantación de identidad  <br/> |SUPLANTACIÓN DE LA  <br/> |[Directiva contra suplantación de identidad](https://go.microsoft.com/fwlink/?linkid=864553), [inteligencia de suplantación](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) <br/> |Sólo ATP  <br/> |
|5  <br/> |Correo no deseado  <br/> |SPM  <br/> |[Directiva de filtro de contenido hospedado](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Todos los clientes  <br/> |
|6  <br/> |Masiva  <br/> |MASIVA  <br/> |[Directiva de filtro de contenido hospedado](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Todos los clientes  <br/> |
|7  <br/> |Suplantación de dominio  <br/> |DIMP  <br/> |[Directiva contra suplantación de identidad](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |Sólo ATP  <br/> |
|8  <br/> |Suplantación de usuario  <br/> |UIMP  <br/> |[Directiva contra suplantación de identidad](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |Sólo ATP  <br/> |
   
Si dispone de varias directivas de Anti-phishing diferentes, se aplicará el uno en la prioridad más alta. Por ejemplo, suponga que tiene dos directivas:
  
|**Directiva**|**Priority**|**Suplantación de usuario o dominio**|**Contra la suplantación**|
|:-----|:-----|:-----|:-----|
|A  <br/> |1  <br/> |Activado  <br/> |Desactivado  <br/> |
|B  <br/> |2  <br/> |Off  <br/> |Activado  <br/> |
   
Si un mensaje se presenta en y se identifica como suplantación de suplantación de identidad y de usuario, el mismo conjunto de usuarios se limita a la directiva de A y B de la directiva y, a continuación, el mensaje se trata como una dirección falsa pero no se aplica ninguna acción con respecto a la suplantación de identidad está desactivado , y SUPLANTACIÓN de la que se ejecuta en una prioridad superior (4) suplantación de usuario (8).
  
Para que otros tipos de suplantación de identidad aplicar directiva, deberá ajustar la configuración de la que se aplican las directivas de diversos a.
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>Escenarios legítimos para deshabilitar contra la suplantación

Mejor contra la suplantación protege a los clientes frente a ataques de suplantación de identidad y, por lo tanto, se recomienda encarecidamente no deshabilitar protección contra la suplantación. Si lo deshabilita, puede resolver algunos falsos positivos a corto plazo, pero a largo plazo que se mostrarán a más riesgo. El costo de la configuración de la autenticación en el lado del remitente, o realizar ajustes en las directivas de suplantación de identidad, son eventos normalmente únicas o requieren mantenimiento periódico, sólo mínima. Sin embargo, el costo para recuperarse de un ataque de suplantación de identidad donde se ha expuesto los datos o los activos que han sido en riesgo es mucho más alta.
  
Por este motivo, es mejor funciona a través de contra la suplantación falsos positivos que para deshabilitar la protección contra suplantación.
  
Sin embargo, hay un escenario legítimo donde debe deshabilitarse contra la suplantación, y que es cuando hay adicional filtrado de correo productos en el enrutamiento de mensajes y Office 365 no es el primer salto en la ruta de acceso de correo electrónico:
  
![Registro de MX del cliente no hace referencia a Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
El otro servidor puede ser un servidor de correo local de Exchange, un dispositivo como Ironport, el filtrado de correo o servicio hospedado de otra en la nube.
  
Si el registro MX del dominio del destinatario no apunta a Office 365, no es necesario deshabilitar contra la suplantación porque Office 365 busca el registro MX de su dominio receptor y suprime contra la suplantación apunta a otro servicio. Si no sabe si su dominio tiene otro servidor en la parte frontal, puede usar un sitio Web al igual que el cuadro de herramientas de MX para buscar el registro MX. Puede que diga algo parecido a lo siguiente:
  
![Registro MX indica el dominio no señala a Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
Este dominio tiene un registro MX que señala a Office 365, por lo que Office 365 no se aplican contra la suplantación de cumplimiento.
  
Sin embargo, si el registro MX de los destinatarios del dominio *does* apunte a Office 365, incluso aunque haya otro servicio delante de Office 365, a continuación, debe deshabilitar contra la suplantación. El ejemplo más habitual es mediante el uso de una destinatario de reescritura: 
  
![Diagrama de enrutamiento de reescritura de destinatario](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
El registro MX del dominio contoso.com apunta al servidor local, mientras que el registro MX del dominio @office365.contoso .net apunta a Office 365 porque contiene \*. protection.outlook.com, o \*. eo.outlook.com en el registro MX:
  
![Puntos de registro MX a Office 365, por lo tanto, probablemente destinatario de reescritura](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
No olvide diferenciar al registro MX de un dominio destinatario no hace referencia a Office 365, y al que se ha sometido a una destinatario de reescritura. Es importante saber la diferencia entre estos dos casos.
  
Si no está seguro de si su dominio receptor ha sufrido una reescritura de destinatario, a veces puede saber mirando los encabezados de mensaje.
  
un) en primer lugar, mire los encabezados en el mensaje para el dominio de destinatario en el encabezado de resultados de autenticación: 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

El dominio de destinatario se encuentra en el texto de color rojo negrita anteriormente, en este caso office365.contoso.net. Esto puede ser diferente que el destinatario en la línea para: encabezado:
  
Para: Destinatario de ejemplo \<destinatarios @ contoso.com\>
  
Realizar una búsqueda de registro MX del dominio del destinatario real. Si contiene \*. protection.outlook.com, mail.messaging.microsoft.com, \*. eo.outlook.com o mail.global.frontbridge.com, que significa que la MX apunta a Office 365.
  
Si no contiene esos valores, a continuación, significa que la MX no señala a Office 365. Una herramienta que puede utilizar para comprobar esto es el cuadro de herramientas de MX.
  
Para este ejemplo en particular, lo siguiente dice que contoso.com, el dominio que tiene el aspecto del destinatario ya que era para: encabezado, tiene puntos de registro MX a un servidor en prem:
  
![Registro MX apunta al servidor on prem](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
Sin embargo, el destinatario real es office365.contoso.net cuyo registro MX apuntar a Office 365:
  
![MX apunta a Office 365, debe ser destinatario reescritura](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
Por lo tanto, este mensaje es probable que ha sufrido una reescritura de destinatario.
  
b) en segundo lugar, asegúrese de distinguir entre los casos de uso comunes de destinatario reescribe. Si va a volver a escribir el dominio de destinatario para \*. onmicrosoft.com, en su lugar, vuelva a escribirla para \*. mail.onmicrosoft.com.
  
Una vez que haya identificado el dominio de destinatario final que se enruta detrás de otro servidor y el registro MX del dominio de destinatario realmente apunta a Office 365 (como publicado en sus registros DNS), puede continuar para deshabilitar contra la suplantación.
  
Recuerde que no desea deshabilitar contra la suplantación si el primer salto en la ruta de acceso de enrutamiento del dominio es Office 365, sólo cuando está detrás de uno o varios servicios.
  
### <a name="how-to-disable-anti-spoofing"></a>Cómo deshabilitar contra la suplantación

Si ya tiene una directiva de Anti-phishing creada, establezca el parámetro EnableAntispoofEnforcement en $false: 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

Si no conoce el nombre de la directiva (o directivas) para deshabilitar, puede mostrarlos: 
  
```
Get-AntiphishPolicy | fl Name
```

Si no dispone de las directivas contra suplantación de identidad existentes, puede crear uno y, a continuación, deshabilitarla (incluso si no tiene una directiva de, contra la suplantación es aún más adelante en 2018; aplicado, se creará una directiva predeterminada para usted y, a continuación, puede deshabilitar en lugar de crear uno) . Debe hacerlo en varios pasos: 
  
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
# Finally, scope the antiphishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false 

```

Deshabilitar contra la suplantación sólo está disponible a través del cmdlet (más adelante en Q2 2018 estará disponible en la seguridad &amp; centro de cumplimiento). Si no tiene acceso a PowerShell, cree un vale de soporte técnico.
  
Recuerde que esto sólo se puede aplicar a los dominios que se sincronizan enrutamiento indirecto cuando enviados a Office 365. Resista la tentación de deshabilitar contra la suplantación debido a algunos falsos positivos, será mejor a largo plazo trabajar con ellos.
  
### <a name="information-for-individual-users"></a>Información para usuarios individuales

Los usuarios individuales están limitados en cómo pueden interactuar con la sugerencia de seguridad contra la suplantación. Sin embargo, hay varias cosas que puede hacer para resolver escenarios comunes.
  
### <a name="common-scenario-1---mailbox-forwarding"></a>Escenario común #1: transferencia de buzón de correo

Si usa otro servicio de correo electrónico y reenviar su correo electrónico para Office 365 o Outlook.com, el correo electrónico se pueden marcar como suplantación de identidad y recibir una sugerencia de seguridad de color rojo. Planeación de Office 365 y Outlook.com a solucionar automáticamente cuando el reenviador es uno de los Outlook.com, Office 365, Gmail o cualquier otro servicio que usa el [Protocolo de arco](https://arc-spec.org). Sin embargo, hasta que se haya implementado esa corrección, los usuarios deben usar la característica de las cuentas conectadas para importar sus mensajes directamente, en lugar de usar la opción de reenvío.
  
Para configurar cuentas conectadas en Office 365, seleccione el icono del engranaje en la esquina superior derecha de la interfaz web de Office 365 \> correo \> correo \> cuentas \> conectado a las cuentas.
  
![Opción de las cuentas de Office 365 - conectado](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
En Outlook.com, el proceso es el icono del engranaje \> opciones \> correo \> cuentas \> conectado a las cuentas.
  
### <a name="common-scenario-2---discussion-lists"></a>Listas de discusiones de escenario común #2:

Las listas de discusión se sabe que tiene problemas con contra la suplantación debido a la forma en reenviar el mensaje y modificar su contenido aún conserva el original desde: dirección.
  
Por ejemplo, suponga que su dirección de correo electrónico es usuario @ contoso.com, y que está interesados en pájaro mirando y unirse a la birdwatchers de la lista de discusión @ ejemplo.com. Al enviar un mensaje a la lista de discusión, puede enviarla de este modo:
  
**Desde:** Arturo López \<usuario @ contoso.com\> 
  
**A:** Lista de discusión de birdwatcher \<birdwatchers @ ejemplo.com\> 
  
**Asunto:** Visión de gran calidad de jays azul en la parte superior de Rainier monte esta semana 
  
¿Cualquier persona desea desproteger la visualización esta semana de Monte Rainier?
  
Cuando la lista de correo electrónico recibe el mensaje, dar formato al mensaje, modificar su contenido y reproducirlo de nuevo para el resto de los miembros en la lista de discusión que se compone de los participantes de muchos receptores de correo electrónico diferentes.
  
**Desde:** Arturo López \<usuario @ contoso.com\> 
  
**A:** Lista de discusión de birdwatcher \<birdwatchers @ ejemplo.com\> 
  
**Asunto:** [BIRDWATCHERS] Visión de gran calidad de jays azul en la parte superior de Rainier monte esta semana 
  
¿Cualquier persona desea desproteger la visualización esta semana de Monte Rainier?
  
---
  
Este mensaje se envió a la lista de discusión de Birdwatchers. Puede cancelar su suscripción en cualquier momento.
  
En el anterior, el mensaje reproducido tiene el mismo desde: dirección (usuario @ contoso.com), pero el mensaje original se ha modificado mediante la adición de una etiqueta a la línea de asunto y un pie de página a la parte inferior del mensaje. Este tipo de modificación del mensaje es común en las listas de distribución de correo y puede provocar falsos positivos.
  
Si usted o alguien de su organización es un administrador de la lista de correo, es posible que pueda configurarlo para pasar comprobaciones contra la suplantación.
  
- Compruebe las preguntas más frecuentes en DMARC.org: [operar una lista de correo y quiero interoperar con DMARC, ¿qué debo hacer?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)
    
- Lea las instrucciones que aparecen en esta entrada de blog: [una sugerencia para los operadores de la lista de correo interoperar con DMARC para evitar errores](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)
    
- Considere la posibilidad de instalar actualizaciones en el servidor de la lista de correo para permitir el arco, vea[https://arc-spec.org](https://arc-spec.org/)
    
Si no tiene la propiedad de la lista de correo:
  
- Puede solicitar el mantenedor de la lista de correo para implementar una de las opciones anteriores (también deben tener configurado para el dominio de que la lista de correo es la retransmisión desde la autenticación de correo electrónico)
    
- Puede crear reglas de buzón de correo en su cliente de correo electrónico para mover mensajes a la Bandeja de entrada. También puede solicitar las reglas de permitir que los administradores de la organización para configurar o reemplazos como describen en la sección Managing remitentes legítimos que va a enviar correo electrónico sin autenticar
    
- Puede crear un vale de soporte técnico con Office 365 para crear un reemplazo de la lista de distribución de correo para tratar como legítimos
    
### <a name="other-scenarios"></a>Otros escenarios

1. Si ninguno de los escenarios comunes anteriores se aplica a su situación, informar el mensaje como un falso positivo de copia a Microsoft. Para obtener más información, vea la sección [cómo ¿informar de los mensajes de correo no deseado o que no sean de correo no deseado a Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) más adelante en este artículo. 
    
2. También puede ponerse en contacto con su administrador de correo electrónico que puede provocar como un vale de soporte técnico con Microsoft. El equipo de ingeniería de Microsoft va a investigar por qué el mensaje se marcó como una dirección falsa.
    
3. Además, si sabe que el remitente es y esté seguro de no están suplantación malintencionada, puede responder al remitente que indica que están enviando mensajes desde un servidor de correo que no se autentica. Esto da como resultado a veces en el remitente original ponerse en contacto con su administrador de TI que va a configurar los registros de correo electrónico requiere autenticación.
  
Cuando suficiente remitentes respondan a los propietarios de dominio que deben configurar los registros de autenticación de correo electrónico, lo cual insta ellos en realizar ninguna acción. Mientras Microsoft también funciona con los propietarios de dominios para publicar los registros necesarios, ayuda a incluso más cuando los usuarios individuales lo solicitan.
    
4. Opcionalmente, puede agregar el remitente a la lista de remitentes seguros. Sin embargo, tenga en cuenta que si un atacante suplanta esa cuenta, se entregarán a su buzón de correo. Por lo tanto, esta opción debe usarse con moderación.
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>¿Cómo deben preparar los remitentes a Microsoft para la protección contra la suplantación

Si es un administrador que actualmente se envía mensajes a Microsoft, Office 365 o en Outlook.com, debe asegurarse de que su correo electrónico se ha autenticado correctamente en caso contrario, es posible que estar marcado como spam o phishing. 
  
### <a name="customers-of-office-365"></a>Clientes de Office 365

Si usted es un cliente de Office 365 y usar Office 365 para enviar correo electrónico saliente:
  
- Para los dominios, [Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)
    
- Para los dominios principales, [Use DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](https://technet.microsoft.com/en-us/library/mt695945%28v=exchg.150%29.aspx)
    
- [Considere la posibilidad de configurar registros DMARC](https://technet.microsoft.com/en-us/library/mt734386%28v=exchg.150%29.aspx) para su dominio para determinar quiénes son los remitentes legítimos 
    
Microsoft no proporciona instrucciones de implementación detallado para cada uno de SPF, DKIM y DMARC. Sin embargo, hay una gran cantidad de información publicada en línea. También hay compañías 3ª dedicada a ayudar a su organización a configurar los registros de la autenticación de correo electrónico.
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>Administradores de dominios que no son clientes de Office 365

Si es un administrador de dominio, pero no es un cliente de Office 365:
  
- Debe configurar SPF para publicar direcciones IP de envío de su dominio y también configurar DKIM (si está disponible) para firmar digitalmente los mensajes. También puede considerar la configuración de registros DMARC.
    
- Si tiene masivo que se transmite el correo electrónico en su nombre, debe trabajar con ellos para enviar correo electrónico de forma tal que el dominio en el campo de envío: dirección (si le pertenece) se alinea con el dominio que pasa SPF o DMARC.
    
- Si tiene in situ en los servidores de correo o enviar desde un proveedor de Software como servicio, o desde un servicio de hospedaje en la nube como Microsoft Azure, GoDaddy, Rackspace, servicios Web de Amazon o similar, debe asegurarse de que se agregan a su registro SPF.
    
- Si es un dominio pequeño que está hospedado en un ISP, debe configurar el registro de SPF según las instrucciones que es proporcionado por el ISP. La mayoría de ISP proporcionan estos tipos de instrucciones y pueden encontrarse en las páginas de soporte técnico de la empresa.
    
- Incluso si no ha mantenido para registros de la autenticación de correo electrónico antes de publicar y ha funcionado correctamente, aún debe publicar registros de la autenticación de correo electrónico para enviar a Microsoft. Al hacerlo, se ayudar en la lucha contra la suplantación de identidad y reduce la posibilidad de que usted, o las organizaciones que enviar a, obtendrá phished.
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>¿Qué ocurre si no sabe quién envía el correo electrónico como su dominio?

Cuántos dominios no publicar registros de SPF porque no sabe que son sus todos los remitentes. Está bien, no es necesario saber que todos ellos son. En su lugar, debe empezar por publicar un registro SPF para los que se conoce, especialmente donde se encuentra el tráfico corporativo y publicar una directiva de SPF neutra,? todos los:
  
example.com IN TXT "v = spf1 include:spf.example.com? todos los"
  
La directiva de SPF neutra significa que cualquier correo electrónico que proviene de fuera de la infraestructura corporativa pasará la autenticación de correo electrónico en absoluto otros receptores de correo electrónico. Correo electrónico que provengan de remitentes de que no sabe acerca se revertirá a neutral, que es casi el mismo que ningún registro SPF de publicación en absoluto.
  
Cuando se envía a Office 365, correo electrónico que proviene el tráfico de su empresa se marcarán como autenticado, pero el correo electrónico que provengan de orígenes de que no sabe acerca aún se puede marcar como falso (dependiendo de si Office 365 implícitamente puede autenticarlo). Sin embargo, sigue siendo una mejora de todo el correo electrónico que se está marcado como suplantación de Office 365.
  
Una vez que ha llegado iniciado con un registro SPF con una directiva de reserva de? todos los puede incluir gradualmente infraestructura más envío y, a continuación, publicar una directiva más estricta. 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>¿Qué ocurre si usted es el propietario de una lista de correo?

Vea la sección [listas de escenario común #2: discusión](#common-scenario-2---discussion-lists). 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>¿Qué ocurre si son un proveedor de infraestructura como un proveedor de servicios de Internet (ISP), el proveedor de servicio de correo electrónico (ESP) o la nube que hospeda el servicio?

Si hospedar correo electrónico de un dominio, y envía correo electrónico o proporcionar la infraestructura de hospedaje que puede enviar correo electrónico, haga lo siguiente:
  
- Asegúrese de que los clientes disponen de documentación que detalla qué publicar en sus registros de SPF
    
- Considere la posibilidad de firma DKIM firmas en el correo electrónico saliente, incluso si el cliente no establece explícitamente seguridad (inicio de sesión con un dominio predeterminado). Puede incluso doble inicio de sesión del correo electrónico con las firmas DKIM (una vez con el dominio del cliente si ha configurado y una segunda vez con firma DKIM de su compañía)
    
No se garantiza que entregabilidad a Microsoft incluso si autenticar correo electrónico que se originan desde la plataforma, pero al menos garantiza que Microsoft no su correo electrónico no deseado debido a que no se autentica. Para obtener más detalles alrededor de cómo Outlook.com filtros de correo electrónico, vea la [página del Administrador de Outlook.com](https://postmaster.live.com/pm/postmaster.aspx).
  
Para obtener más detalles sobre los procedimientos recomendados de proveedores de servicio, consulte [M3AAWG Mobile mensajería prácticas recomendadas para los proveedores de servicios](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).
  
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="why-is-microsoft-making-this-change"></a>¿Por qué Microsoft está realizando este cambio?

Porque el impacto de suplantación de identidad ataques y debido a que la autenticación de correo electrónico ha sido alrededor de más de 15 años, Microsoft cree que el riesgo de continuar permitir que el correo electrónico sin autenticar es mayor que el riesgo de perder correo electrónico legítimo.
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>¿Este cambio provocará correo electrónico legítimo que se marcará como correo no deseado?

En primer lugar, habrá algunos mensajes marcados como correo no deseado. Sin embargo, con el tiempo, se ajustarán los remitentes y, a continuación, la cantidad de mensajes etiquetados como falso será insignificante para la mayoría de las rutas de acceso de correo electrónico.
  
En primer lugar, Microsoft propio adoptado esta característica varias semanas antes de implementar para el resto de sus clientes. Mientras se ha producido una interrupción en primer lugar, gradualmente rechazada.
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>¿Microsoft pondrá esta característica a Outlook.com y que no sean - avanzada protección contra amenazas de los clientes de Office 365?

Protección contra la suplantación se inicialmente implementarán a los clientes de ATP/E5 y puede liberarse en el futuro a los otros usuarios. Sin embargo, si lo hace, es posible que algunas funciones que no se aplican como informes y custom anula.
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>¿Cómo puedo informar los mensajes de correo no deseado o que no sean de correo no deseado volver a Microsoft?

Puede usar el [mensaje de informe de complemento para Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), o si no está instalado, [envío de correo no deseado, que no sean de correo no deseado y mensajes de estafas de suplantación de identidad a Microsoft para su análisis](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx).
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>Soy un administrador de dominio que no sabe que son de todos los remitentes de Mis!

Consulte [los administradores de dominios que son no los clientes de Office 365](#administrators-of-domains-that-are-not-office-365-customers).
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>¿Qué sucede si desactiva la protección contra la suplantación de mi organización, aunque Office 365 es mi principal filtro?

No se recomienda esto porque se mostrarán a la suplantación de identidad más perdida y mensajes seguros. Es la falsificación de suplantación de identidad no todas las y se omitirán todos los no suplantar. Sin embargo, el riesgo será superior a un cliente que permite contra la suplantación.
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>¿Habilitación de la protección contra la suplantación significa que estará protegido frente a todos los de la suplantación de identidad?

Desafortunadamente, no, puesto que se adaptan los suplantadores de identidad para usar otras técnicas, como en peligro las cuentas o cómo configurar cuentas de servicios gratuitos. Sin embargo, la protección contra suplantación de identidad mucho mejor funciona para detectar estos otros tipos de métodos de suplantación de identidad debido a que la protección de Office 365 capas están diseñadas trabajo conjuntamente y crear uno encima de otro.
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>¿Otros receptores de correo electrónico de gran tamaño bloquear correo electrónico no autenticado?

Casi todos los receptores de correo electrónico de gran tamaño implementan tradicional SPF, DKIM y DMARC. Algunos receptores tienen otras comprobaciones que son más estrictas que acaba de esos estándares, pero pocos vaya como Office 365 para bloquear no autenticado de correo electrónico y los trata como una dirección falsa. Sin embargo, la mayor parte de la industria es cada vez más estrictos acerca de este tipo concreto de correo electrónico, especialmente debido al problema de suplantación de identidad.
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>¿Necesita la opción avanzada de filtrado de correo no deseado habilitada para "SPF disco duro Fail" si se habilita contra la suplantación?

No, esta opción ya no es necesaria porque la característica contra la suplantación no sólo tiene en cuenta se produce un error al disco duro de SPF, pero un conjunto mucho más amplio de criterios. Si tiene contra la suplantación habilitada y un error de disco duro SPF habilitada la opción, es probable que obtiene más falsos positivos. Se recomienda deshabilitar esta característica, tal y como aparecería no proporcionar casi catch adicional para spam o phishing y en su lugar generar principalmente falsos positivos.
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>¿Combinación de reescritura de direcciones de remitente (SRS) ayuda a corregir el reenvío de correo electrónico?

SRS sólo parcialmente corrige el problema de correo electrónico reenviados. Al volver a escribir el SMTP MAIL FROM, SRS puede garantizar que las pasadas de mensaje reenviado SPF en el destino siguiente. Sin embargo, debido a que contra la suplantación se basa en el campo de: dirección en combinación con el dominio la MAIL FROM o firma de DKIM (u otras señales), no es suficiente evitar que el correo electrónico reenviados que se marca como suplantación.
  

