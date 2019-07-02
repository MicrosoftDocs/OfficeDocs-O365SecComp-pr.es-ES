---
title: Crear listas de remitentes seguros en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 4/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Si desea asegurarse de que recibe el correo de un remitente determinado, ya que confía en ellos y sus mensajes, puede ajustar la lista de permitidos en una directiva de filtro de correo no deseado en el centro de administración de Exchange.
ms.openlocfilehash: 4526441c68d187e644a06228c5b1be820968524a
ms.sourcegitcommit: 044003455eb36071806c9f008ac631d54c64dde6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2019
ms.locfileid: "35199585"
---
# <a name="create-safe-sender-lists-in-office-365"></a>Crear listas de remitentes seguros en Office 365

Si quiere asegurarse de que los usuarios reciben mensajes de correo electrónico de un remitente o remitentes concretos, ya que confía en ellos y sus mensajes, hay varios métodos disponibles que puede elegir. Estas opciones incluyen reglas de transporte de Exchange (ETR), remitentes seguros de Outlook, listas de direcciones IP permitidas, remitente/dominio de correo electrónico no deseado.

> [!IMPORTANT]
> Aunque las listas de permitidos de la organización se pueden usar para solucionar falsos positivos, esto debe considerarse una solución temporal y evitarse si es posible. No se recomienda la administración de falsos positivos mediante listas de permitidos, ya que puede abrir involuntariamente su organización para la suplantación, la suplantación y otros ataques. Si va a usar una lista de permitidos para este propósito, tendrá que estar atento y mantener el artículo sobre el envío de correo no deseado [, correo no deseado y mensajes de suplantación de identidad (phishing) a Microsoft para su análisis](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), en la lista desplegable.

El método recomendado para configurar una lista de remitentes seguros es usar las reglas de transporte de Exchange (ETR), ya que esto supone la máxima flexibilidad para asegurarse de que solo se permiten los mensajes correctos. *Las listas de permitidos basadas en dominios* y *direcciones de correo electrónico de la Directiva contra correo no deseado* no son tan seguras como *las listas basadas en direcciones IP* , ya que los dominios se pueden suplantar fácilmente. Pero las listas de permitidos basadas en IP de la Directiva contra correo no deseado también presentan los riesgos, ya que permiten que los dominios enviados a través de esa IP omitan el filtrado de correo no deseado. Tenga cuidado y supervise *las* excepciones realizadas, con cuidado.

> [!IMPORTANT]
> [Aquí](create-block-sender-lists-in-office-365.md)encontrarás información sobre cómo crear una **lista de remitentes bloqueados** .

## <a name="options-from-most-to-least-recommended"></a>Se recomiendan opciones de mayor a menor

Siempre debe restringir las listas de permitidos porque omiten muchas medidas de seguridad. Debe volver a comprobar todas las listas de permitidos como parte de su mantenimiento estándar para conocer quién está autorizado a omitir. La recomendación es usar ETR restrictivas siempre que sea posible.

- Reglas de transporte de Exchange (ETR también denominadas reglas de flujo de correo)
- Remitentes seguros de Outlook
- Directiva contra correo no deseado: listas de direcciones IP permitidas
- Directiva contra correo no deseado: listas de permitidos de remitente/dominio

## <a name="using-exchange-transport-rules-etrs-to-allow-specific-senders-recommended"></a>Uso de reglas de transporte de Exchange (ETR) para permitir remitentes específicos (recomendado)

Para asegurarse de que solo se permiten mensajes legítimos en la organización, la condición debe ser una de las siguientes:

- Use el estado de autenticación del remitente del dominio de envío. Esto se realiza comprobando el encabezado Authentication-Results para asegurarse de que contiene "dMarc = pass" o "dMarc = bestguesspass". Esto garantiza que el dominio de envío se ha autenticado y no se está falsificando. Haga clic para obtener más información sobre la autenticación de correo electrónico de [SPF](https://docs.microsoft.com/en-us/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)y [DMARC](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-dmarc-to-validate-email) .

- O bien, si el dominio remitente no tiene autenticación, use el dominio remitente *más* una IP de envío (o intervalo IP). Asegúrese de que es lo más *restrictiva posible*, el objetivo es que lo haga de la forma más segura posible. *No* se recomienda un intervalo IP mayor que/24. Evite agregar intervalos de direcciones IP que pertenezcan a servicios de consumo o infraestructuras compartidas.

> [!IMPORTANT]
> Si permite una dirección IP NATted, debe conocer los equipos que participan en el grupo de NAT para conocer el ámbito de su permiso. Tenga en cuenta que las direcciones IP pueden cambiar y también pueden ser participantes de NAT. Debe volver a comprobar todas las listas de permitidos, incluida la IP permite como parte de su mantenimiento estándar.

- *Si lo*desea, puede Agregar una condición que el mensaje origine desde fuera de la organización (esto es implícito, pero es adecuado agregarlo como condición para tener en cuenta los servidores locales que puede que no estén correctamente configurados).

- *Opcionalmente*, si puede identificar cualquier palabra clave o frase única en el asunto o el cuerpo del correo electrónico, use esta información como condición adicional para restringir aún más los mensajes de correo electrónico permitidos por la regla de flujo de correo.

La acción de la regla debe seguir este patrón:

1. Establezca el nivel de confianza contra correo no deseado (SCL) en-1 (pase por alto el filtrado de correo no deseado).

2. Agregue un encabezado X para indicar lo que hace la regla. En el ejemplo siguiente, puede Agregar un encabezado sencillo "X-ETR: omitir el filtrado de correo no deseado para `contoso.com`el remitente autenticado". Si tiene más de un dominio en esta regla, puede cambiar el texto del encabezado según corresponda. **Cuando un mensaje omite el filtrado debido a un ETR, marca SFV: SKN en el encabezado X-Forefront-antispam-Report** (**si está en una lista de direcciones IP permitidas, también marca IPV: cal**). Esto le ayudará con la solución de problemas.

![GUI para omitir el filtrado de correo no deseado.](media/1-AllowList-SkipFilteringFromContoso.png)

> [!CAUTION]
> No configure reglas de flujo de correo solo con *el dominio del remitente* como una condición para omitir el filtrado de correo no deseado. Este método aumenta significativamente el riesgo de que los remitentes de correo no deseado suplanten el dominio remitente (o suplantar la dirección de correo electrónico completa) omitir el filtrado de correo no deseado, las comprobaciones de autenticación de remitente y el mensaje llegará a la bandeja de entrada de una persona.

![Cómo establecer el SCL en menos de uno.](media/2-AllowList-SetsSCLMinus1.png)

No agregue dominios de su propiedad o de dominios populares (por ejemplo `microsoft.com`,) a la regla de flujo de correo como una condición. Esto se considera un riesgo alto, ya que crea oportunidades para que los actores incorrectos le envíen correo que, de lo contrario, se filtraría.

[Haga clic en para conocer los pasos para crear un ETR, también conocido como reglas de flujo de correo](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages).

## <a name="use-outlook-safe-senders-end-user-managed"></a>Usar remitentes seguros de Outlook (administrado por el usuario final)

En lugar de autorizar una dirección, un dominio o una dirección IP de forma global, los usuarios finales también pueden permitir el envío de direcciones a través de remitentes seguros de Outlook. Los pasos para configurar esto difieren entre [Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46) y el [cliente de Outlook](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Cuando los mensajes se hayan autorizado correctamente debido a que los remitentes seguros verán SFV: SFE en el X-Forefront-antispam-Report** , lo que indica que se omitirá el filtrado de correo no deseado/falso/phish.

## <a name="use-anti-spam-policy-ip-allow-lists"></a>Usar listas de direcciones IP permitidas de la Directiva contra correo no deseado

Cuando no es posible usar ETR para permitir globalmente a un remitente específico mientras se valida la autenticación del remitente, o al asociar un dominio y una IP juntos, la siguiente mejor opción es agregar el remitente a la *lista de direcciones IP permitidas de la Directiva contra correo no deseado*. [Puede encontrar los pasos detallados en Configure the Connection Filter Policy Document](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy). Es importante mantener la lista de direcciones IP permitidas en el mínimo y evitar usar intervalos de direcciones IP. Evite agregar intervalos de direcciones IP que pertenezcan a servicios de consumo o infraestructuras compartidas y *Asegúrese* de revisar la lista de direcciones IP permitidas de forma regular y quitar las que ya no son necesarias.

> [!CAUTION]
> La configuración de las directivas contra el correo no deseado para permitir en función de la dirección IP del remitente sólo hará que se omita el filtrado de correo no deseado para todos los mensajes de esa dirección IP en la regla permitir. Esto crea un riesgo alto de que los actores incorrectos le envíen correo que, de lo contrario, se filtraría. Este método también omite el filtrado de correo no deseado, las comprobaciones de autenticación del remitente y el mensaje que se encuentra en la bandeja de entrada del usuario, lo que aumenta el riesgo.

## <a name="use-anti-spam-policy-senderdomain-allow-lists"></a>Usar listas de remitentes/dominios permitidos de directivas contra correo no deseado

La opción menos deseable es autorizar por remitente o dominio. Esta opción debe evitarse siempre que *sea posible* , ya que pasa por completo la protección contra correo no deseado/suplantación de identidad (phishing) y no evalúa la autenticación del remitente. Este método aumenta el riesgo de recibir correo de actores incorrectos y es la mejor opción recomendada temporalmente y solo cuando se realicen pruebas. Puede encontrar los pasos detallados en [configurar las directivas de filtro de correo no deseado](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies) .

> [!CAUTION]
> La configuración de las directivas contra el correo no deseado para permitir que el *remitente o el dominio permita* que los mensajes omitan el filtrado de correo no deseado para a) los mensajes de los remitentes de la lista de permitidos, o b, todos los remitentes de un dominio permitido. Este método aumenta significativamente el riesgo de que los remitentes de correo no deseado suplanten el dominio remitente (o suplantar la dirección de correo electrónico completa) que omiten el filtrado de correo no deseado, las comprobaciones de autenticación del remitente y envían el mensaje directamente a la bandeja de entrada de una persona.
> 
> No agregue dominios que sean de su propiedad o de dominios populares `microsoft.com`(por ejemplo,) a la regla de flujo de correo como una condición. Este método se considera un riesgo alto, ya que crea oportunidades para que los actores incorrectos le envíen correo que, de lo contrario, se filtraría, lo que aumentaría el riesgo.

> [!IMPORTANT]
> [Aquí](create-block-sender-lists-in-office-365.md)encontrarás información sobre cómo crear una **lista de remitentes bloqueados** .